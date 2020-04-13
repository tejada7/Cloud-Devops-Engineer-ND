setup:
    python3 -m venv ~/.myrepo

install:
    pip install --upgrade pip &&\
        pip install -r requirements.txt

test:
    # python -m pytest -vv --cov=myrepolib tests/*.py
    # python -m pytest --nbval notebook.ipynb

lint:
    hadolint demos/flask-sklearn/Dockerfile
    pylint --disable=R,C,W1203 demos/**/**.py

all: install lint test