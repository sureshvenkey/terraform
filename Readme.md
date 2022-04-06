# Storing terraform states in aws s3 in workspace model
## Install Ubuntu in windows 10
1. Open the Start menu and search for "Turn Windows features on or off".  
```$ sudo apt-get update  
$ sudo apt-get install software-properties-common  
$ sudo apt-add-repository ppa:ansible/ansible    
$ sudo apt-get update  
$ sudo apt-get install ansible -y  
```
2. Scroll down through the list of features until you see Windows Subsystem for Linux. Click on the checkbox, and then click OK to enable the feature.  
3. Open the Microsoft Store. Search for Ubuntu and click on Get to install the latest version.  
4. Once the installation is complete, click on Launch to start up the Ubuntu command terminal.  
## Terraform installation in windows 10 Ubuntu
```
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -  
sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"  
sudo apt install terraform  
```
## Install the aws cli in windows10 
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
## Configure aws profile for dev, uat and prod aws accounts
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html
### Different aws accounts are created for dev, uat and prod environments
Switch aws cli profiles   
(Linux)AWS CLI v1  -->  export AWS_DEFAULT_PROFILE=user2   
(Linux)AWS CLI v2  -->  export AWS_PROFILE=user2   
(Windows)AWS CLI v1  -->  set AWS_DEFAULT_PROFILE=user2   
(Windows)AWS CLI v2  -->  set AWS_PROFILE=user2   
## Create TF files for backend with workspace.
https://blog.knoldus.com/workspaces-in-terraform/

## How to run Ansible without specifying the inventory but the host directly using ansible-palybook flags?  
Surprisingly, the trick is to append a ,
The host parameter preceding the , can be either a hostname or an IPv4/v6 address.
```
ansible all -i example.com,  
ansible all -i 93.184.216.119,  
ansible-playbook -i example.com, playbook.yml   # Requires 'hosts: all' in the playbook  
ansible-playbook -u ec2-user -i 93.184.216.119, --private-key aws.pem ansible_excel.yaml  
```
## How to use Ansible with Terraform  
https://alex.dzyoba.com/blog/terraform-ansible/  
