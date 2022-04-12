# Terraform getting Started
To learn terraform, all uou need is to get your hands dirty. Here are the steps needed for installing terrafrom in your windows 10 laptop.  
### Install Ubuntu in windows 10
1. Open the Start menu and search for "Turn Windows features on or off".  
2. Scroll down through the list of features until you see Windows Subsystem for Linux. Click on the checkbox, and then click OK to enable the feature.  
3. Open the Microsoft Store. Search for Ubuntu and click on Get to install the latest version.  
4. Once the installation is complete, click on Launch to start up the Ubuntu command terminal. 

### Terraform installation in windows 10 Ubuntu
```
$ curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -  
$ sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"  
$ sudo apt install terraform  
```
Install ansible if you wish to run ansible code using terraform providers.  
### Ansible installation in windows 10 Ubuntu
```$ sudo apt-get update  
$ sudo apt-get install software-properties-common  
$ sudo apt-add-repository ppa:ansible/ansible    
$ sudo apt-get update  
$ sudo apt-get install ansible -y  
```

### Install the aws cli in windows10 
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
## Configure aws profile for dev, uat and prod aws accounts
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html
### Different aws accounts are created for dev, uat and prod environments
Switch aws cli profiles   
(Linux)AWS CLI v1  -->  export AWS_DEFAULT_PROFILE=user2   
(Linux)AWS CLI v2  -->  export AWS_PROFILE=user2   
(Windows)AWS CLI v1  -->  set AWS_DEFAULT_PROFILE=user2   
(Windows)AWS CLI v2  -->  set AWS_PROFILE=user2   
### Create TF files for backend with workspace.
https://blog.knoldus.com/workspaces-in-terraform/

[Next Page: Ansible_with_Terraform ](https://github.com/sureshvenkey/terraform/blob/main/Ansible_with_Terraform.md "Google's Homepage")
