# Storing terraform states in aws s3 in workspace model
## Install Ubuntu in windows 10
1. Open the Start menu and search for "Turn Windows features on or off".  
`$ sudo apt-get update  
$ sudo apt-get install software-properties-common  
$ sudo apt-add-repository ppa:ansible/ansible    
$ sudo apt-get update  
$ sudo apt-get install ansible -y`
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
