# Operationalize Machine Learning Microservice API
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/EvelynAnyebe/project-ml-microservice-kubernetes/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/EvelynAnyebe/project-ml-microservice-kubernetes/tree/main)

## Project Summary
In this project, I operationanlize a working machine learning microservice that predict housing prices in Boston using docker for application containerization and kubernetes for deployment. The repo is integrated with circle ci for linting tests.

## Scripts

The scripts available to test and run this application as described below.

### Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

* Install Docker

* Install hadolint

* Install kubernetes(minikube)

* Install kubectl

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Making Predictions

1. Run in new terminal `./make_prediction.sh`


## File structure

The file structure is described using the root `dir`. When in the root, the following folder and files are available.

* .circleci
  This contains the `config.yml` to enable CI-CD for linting test from the repo.
* model_data
  This contains Boston housing data for the `sklearn` model. You should not modify this folder.
* output_txt_files
  This contains outputs obtained from making prediction after running the app with docker and kubernetes respectively.
* app.py 
   the microservice application

Bash scripts like `make_prediction.sh`, `run_docker.sh`,`upload_docker.sh`,`run_kubernetes.sh` used for application operationalization.

Makefile for environment setup and Dockerfile for application containerization.