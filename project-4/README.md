# Operationalize a Machine Learning Microservice API

## Setup the Environment

* Create a virtualenv and activate it
    - `python3 -m venv ~/.devops`
    - `source ~/.devops/bin/activate`
* Install hadolint `brew install hadolint`
* Install pylint `pip3 install pylint`
* Run `make install` to install the necessary dependencies
* To verify everything is compliant, run `make lint`

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
___
#### Make a prediction
Assuming the application is already running on port 8000, run `./make_prediction.sh`

#### Pushing the docker image to DockerHub
Assuming the application has already been built (through `./run_docker.sh`), then run `./upload_docker.sh`.<br/>
My built image is available [here](https://hub.docker.com/r/tejada7/flask_app).