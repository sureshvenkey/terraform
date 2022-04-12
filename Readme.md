# Terraform getting Started
To learn terraform, all uou need is to get your hands dirty. Here are the steps needed for installing terrafrom in your windows 10 laptop.  
### Install Ubuntu in windows 10
You can install terraform directlly in windows 10 by downloading the supported package from terraform site but if you are planning to call the ansible code along with terraform, we suggest to install Ubuntu os as a sub-system service in windows 10. Then install terraform and ansible in Ubuntu os, Here are the steps for installing Ubuntu in windows 10.     
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

### Install the aws cli in windows10 Ubuntu
```
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
$ unzip awscliv2.zip
$ sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin
-i – This option specifies the directory to copy all of the files to (Default value is /usr/local/aws-cli).
-b – This option specifies that the symolic link to the main aws program to  the install directory (Default value is /usr/local/bin). 
$ ls -l /usr/local/bin/aws
/usr/local/bin/aws -> /usr/local/aws-cli/v2/current/bin/aws
$ aws --version
```
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
## Configure aws profile for dev, uat and prod aws accounts
The below command configures the aws default profile
```
$ aws configure
AWS Access Key ID [None]: AAAAAAAAAAAAAAAAAAAAAAAAAA
AWS Secret Access Key [None]: BBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBBY
Default region name [None]: us-west-2
Default output format [None]: json
```


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
