
login to the linux machine
create a new directory
sudo mkdir projects
cd /projects
clone github repo on the linux.
!
sudo git clone <enter the https url from github repo you have created already>
!
verify if the repo is cloned
ls lha
!
Install virtual environment on the Linux machine
sudo apt install python3.12.-venv
python3 -m venv venv

Active the virtual environment
Go to the directory where virtual environment was installed.
```text
source /venv/bin/activate
```

Install new version of pip

```text
pip install pip --upgrade
```

Install netmiko
```text
pip install netmiko
```

Check ansible docs

```text
ansible-doc -l | grep cisco.ios
```

View details of the modules

```text
ansible-doc cisco.ios.ios_interfaces
```