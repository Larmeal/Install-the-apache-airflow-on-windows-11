# Installation of The Apache Airflow on Windows 11 

### Download the PowerShell 

That is easy steps most of the topic, first of all, you should
> Open the Microfose Store -> Search the "PowerShell" -> Install it.

### Download the Ubuntu and install 
the Ubuntu is the distribution of Linux in this case we use it for running the Apache Airflow

You can open the [Microsoft website](https://learn.microsoft.com/en-gb/windows/wsl/install) and then follow the steps to install the Ubuntu by the PowerShell

1. Run on your Powershell
```
wsl --install
```

2. Examine the whole distributions of Linux software (choose one of paths)
```
wsl -l -o
```
```
wsl --list --online
```

3. You can choose one of the lists but in this case, we decided on "ubuntu-20.04".
```
wsl --install -d Ubuntu-20.04
```

4. To run a specific wsl distribution from within PowerShell without changing your default distribution
```
wsl -d Ubuntu-20.04
```

### Set up the Ubuntu for first-time install 

1. Next step, open the Ubuntu by clicking on the tap of the PowerShell tab bar.
  (if someone doesn't know how to open the PowerShell like this, you just right-click on "start" and use the Windows terminal) 

  ![open ubuntu ](https://user-images.githubusercontent.com/95965281/190912152-918b5043-256b-4d3e-a260-06412bd1e8bc.png)

2. After you are setting the username and password, use run the command belows immediately 
```
sudo apt-get update
```
  then 
```
sudo apt-get upgrade
```
  then
```
sudo apt-get install npm
```

3. Install the python by the Pyenv in the Ubuntu

  the [Stackoverflow](https://stackoverflow.com/questions/62743132/ubuntu-18-04-command-pyenv-not-found-did-you-mean) link clearly describes a step-by-step method. you   can follow Ircbarros's comment

4. Install the python with pyenv (you can determine the version of python in this case use the Python 3.9.12 version.)
```
pyenv install 3.9.12
```

  **optional** for people who use VScode IDE to download the "Remote - WSL" extension to write the python code in Ubuntu

  if you get the error message 
  "pyenv install: 3.x BUILD FAILED (Ubuntu 20.04 using python-build 20180424)"

  do following this [link](https://stackoverflow.com/questions/67807596/pyenv-install-3-x-build-failed-ubuntu-20-04-using-python-build-20180424)

### Download and set up Apache Airflow

The final step of installation of the Apache Airflow 
1. you should create some a folder (or directory) at /home/user location.
```
mkdir airflow-setup
```

2. move to the folder (or directory)
```
cd airflow-setup
```
  you can use "tab" on your keyboard to auto-complete writing the text on the terminal

3. Create a virtual python environment in the airflow-setup directory
```
python3 -m venv ENV
```
  then activate the environment
```
source ENV/bin/activate
```

4. Upgrade your "pip" (Python package manager) to the latest version
```
pip install --upgrade pip
```

5. Run the command belows ([Apache Airflow](https://airflow.apache.org/docs/apache-airflow/stable/installation/installing-from-pypi.html))
```
AIRFLOW_VERSION=2.3.4
PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)"
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"
pip install "apache-airflow[async,postgres,google]==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"
```

6. Start the initial database of Airflow
```
airflow db init
```

7. Start the webserver of Airflow that run on "[localhost:8080](http://localhost:8080/)"
```
airflow webserver
```

8. When we did all the steps previously, The "airflow" directory was created simoustanly with the web server or the initial database command was triggered

