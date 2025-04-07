# Jenkins Python Pipeline

This repository contains a simple Python calculator application and a Jenkins pipeline to demonstrate automated testing and packaging using CI/CD.

## Project Overview

This project includes:

- A basic calculator application written in Python
- Unit tests using Pytest
- A Jenkinsfile defining CI/CD stages
- PyInstaller for packaging the Python script into an executable

## Project Structure


## Jenkins Pipeline Stages

The `Jenkinsfile` defines the following stages:

1. **Install dependencies**  
   Installs the Python packages listed in `requirements.txt`

2. **Run tests**  
   Executes unit tests using Pytest

3. **Package with PyInstaller**  
   Converts the calculator script into a standalone executable

4. **Archive build**  
   Archives the generated executable as a build artifact

## How to Run Tests Locally

1. Install dependencies:
pip install -r requirements.txt
2. Run tests:
pytest test_calculator.py

## Notes

This repository is part of a DevOps CI/CD assignment demonstrating Jenkins automation with GitHub.
