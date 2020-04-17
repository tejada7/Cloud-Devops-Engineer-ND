# Operationalize a Machine Learning Microservice API
[![CircleCI](https://circleci.com/gh/tejada7/Cloud-Devops-Engineer-ND.svg?style=svg)](https://circleci.com/gh/tejada7/Cloud-Devops-Engineer-ND)

This project consists in deploying an elastic and fault-tolerant Machine Learning inference API using Kubernetes, configuring a microservice to be highly available by using Kubernetes best practices.
In addition to that, it validates the design by performing testing using CircleCI. 

## Setup the Environment

* Create a virtualenv and activate it
    - `python3 -m venv ~/.devops`
    - `source ~/.devops/bin/activate`
* Install hadolint `brew install hadolint`
* Install pylint `pip3 install pylint`
* Run `make install` to install the necessary dependencies
* To verify everything is compliant, run `make lint`
___
## Run the app

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

## Make a _prediction_
Assuming the application is already running on port 8000, run `./make_prediction.sh`

## Push the docker image to DockerHub
Assuming the application has already been built (through `./run_docker.sh`), then run `./upload_docker.sh`.<br/>
My built image is available [here](https://hub.docker.com/r/tejada7/flask-app).

## Set up k8s locally
Install minikube and then run `minikube start`. N.B. It might take several minutes to spin up.
___
## File description
- [`app.py`](./app.py) -> _python_ application that contains the microservice backend
- [`docker_out.txt`](./docker_out.txt) -> sample of what the application logs out after _making a prediction_ 
- [`Dockerfile`](./Dockerfile) -> set of instructions to create an image
- [`kubernetes_out.txt`](./kubernetes_out.txt) -> text output after calling `run_kubernetes.sh`
- [`make_prediction.sh`](./make_prediction.sh) -> simulates a client call to the API
- [`Makefile`](./Makefile) -> includes instructions on environment setup and lint tests
- [`requirements.txt`](./requirements.txt) -> list of dependencies to be installed inside the virtual venv when running `make install`
- [`run_docker.sh`](./run_docker.sh) -> builds and runs an image
- [`run_kubernetes.sh`](./run_kubernetes.sh) -> retrieves an image from dockerHub, runs it in a pod and forwards the application port 80 to the host 8080 to be exposed to the client
- [`upload_docker.sh`](./upload_docker.sh) -> pushes a docker local image to dockerHub