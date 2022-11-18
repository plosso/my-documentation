# Terrafrom commands

## Switch the working directory
terrafrom -chdir=<path_to/tf> <subcommmands>

## Initialize the directory
terraform init

## Create an execution plan
terraform plan

## Output a deployment plan
terraform plan -out tfplan.out

## Output a destroy plan
terraform plan -destroy

## Apply changes
terraform apply

## Apply a specfic plan
terraform apply tfplan.out

## Only apply changes to a targeted resource
terraform -target=<resource_name> 

## Pass a variable via the command line
terraform apply -var my_variable=<variable>

## Destroy managed infrastructure
terraform destroy

## Get provider info used on configuration
terraform providers



