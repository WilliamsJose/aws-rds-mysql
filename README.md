
# Terraform AWS RDS

[Manage RDS Instance tutorial](https://developer.hashicorp.com/terraform/tutorials/aws/aws-rds). 

### Requirements 
- install terraform CLI and aws CLI
- configure aws access keys vars from Security Credentials:
  > export AWS_ACCESS_KEY_ID=[your-key-id]   
  > export AWS_SECRET_ACCESS_KEY=[your-key-secret]
- configure db_password as:
  > export TF_VAR_db_password="n3wpass"

### Run
```shell
  terraform init
  terraform apply
```

### Connect
after changing **publicly_accessible** to true
```shell
mysql -h $(terraform output -raw rds_hostname) -P $(terraform output -raw rds_port) -u $(terraform output -raw rds_username) -p
```