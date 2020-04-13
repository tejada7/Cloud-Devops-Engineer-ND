# Title to be updated

Before undertaking the project, the folliwing steps were followed to get the neccesary software to run Docker on my machine: 
- Create a Python3 virtual environment: python3 -m venv venv
- Activate the virtual environment: source venv/bin/activate
- Upgrade pip if you need to (optional): pip install --upgrade pip
- Install pylint: pip install pylint
- Install the code formatting tool black: pip install black
- Install the testing library pytest: pip install pytest
- Install the interactive interpreter ipython: pip install ipython
- Test it out by typing ipython and running some code

To run a Makefile: `make xxx` where xxx is the command present in the file, e.g. install, test, all, etc.

### Exercise 3
Test an application locally with _locust_
`python3 app.py`
`locust -f locustfile.py`
Once in the Locust [GUI](http://127.0.0.1:8089), configure to listen to http://127.0.0.1:8080 and enjoy!