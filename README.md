# FreeRTOS CI/CD Pipeline for Agilex

## Overview
This repository contains the Jenkins configuration for the CI/CD pipeline of the FreeRTOS project on Agilex. The pipeline automates the process of code checkout, building, coding analysis, flashing the board, and executing test cases.

## Prerequisites
- **Jenkins** installed and running.
- Access to the **Ubuntu server** where the project scripts and images are located.
- Necessary tools to be installed:
  - `arm-gnu-toolchain`
  - `LDRA tool`
  - `Quartus command line tools`

## Pipeline Stages
1. **Checkout Code**: Clones the specified branch from the GitLab repository.
2. **Build**: Compiles the code using the `Makefile`.
3. **Coding Analysis**: Runs coding analysis using the LDRA tool and generates reports.
4. **Generate JIC File**: Compiles the project using Quartus to generate the JIC file.
5. **Flashing the Board**: Writes the generated JIC file to the board over JTAG.
6. **Test Framework**: Executes test scripts and validates all test cases.

## Usage
1. Configure Jenkins to point to this repository and create a new pipeline job.
2. Make sure to set up the necessary environment variables and tool paths in Jenkins.
3. Trigger the pipeline either manually or automatically based on GitLab triggers.