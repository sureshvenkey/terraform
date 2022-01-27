# Storing terraform states in aws s3 in workspace model

## Install the aws cli in windows10 
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
## Configure aws profile for dev, uat and prod aws accounts
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html
### Different aws accounts are created for dev, uat and prod environments
Switch aws cli profiles   
AWS CLI v1  -->  export AWS_DEFAULT_PROFILE=user2   
AWS CLI v2  -->  export AWS_PROFILE=user2   
## Create TF files for backend with workspace.
https://blog.knoldus.com/workspaces-in-terraform/
