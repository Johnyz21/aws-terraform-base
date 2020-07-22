# Base Terraform
This terraform project will create a centralised state management solution for my terraform projects. The 
project will create one DynamoDB table used for state locking and an S3 bucket used to store the state files.

***All commands are  to be run in the terraform folder***
# Initialisation
Comment out the block `terraform { backend { ... } }` and initialise the terraform plugins and backend using the command below


`terraform init` 


Run terraform apply to create the S3 bucket and DynamoDB table. The tfstate file will be created by terraform locally.


`terraform apply` 


Uncomment the `terraform { backend { ... } }` block and initialise the new backend with the following command. This will push the local state file to the S3 bucket. Accept any prompts 


`terraform init` 

# Deleting
Comment out the block `terraform { backend { ... } }` and initialise the new backend (which will be local). Accept any prompts 


`terraform init` 


As the state file is now local. We can safely destroy the project
`terraform destroy`
