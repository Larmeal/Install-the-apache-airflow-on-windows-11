# Installation of The Apache Airflow on Windows 11 

### Download the PowerShell 

That is easy steps most of the topic, first of all, you should
> Open the Microfose Store -> Search the "PowerShell" -> Install it.

### Download the Ubuntu and install (the Ubuntu is the distribution of Linux in this case we use it for running the Apache Airflow)

You can open the [Microsoft website](https://learn.microsoft.com/en-gb/windows/wsl/install) and then follow the steps to install the Ubuntu by the PowerShell

or 

1. Run on your Powershell
```
wsl --install
```

2. Examine the whole distributions of Linux software   
```
wsl -l -o
```
or
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

the [Stackoverflow](https://stackoverflow.com/questions/62743132/ubuntu-18-04-command-pyenv-not-found-did-you-mean) link is process clearly 
