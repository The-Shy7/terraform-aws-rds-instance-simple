# terraform-aws-rds-instance-simple
A simple Terraform module that provisions an **Amazon RDS instance** with configurable parameters, including engine type, version, instance class, and storage. It deploys the database within a **non-default VPC** and **private subnets** while also creating supporting resources like a **DB subnet group** and **DB parameter group** if needed.

## Features
- Supports **PostgreSQL** with selectable versions.
- Creates an **RDS instance** with configurable instance class, storage size, and credentials.
- Configures an **RDS subnet group** to specify subnets for the database.
- Defines an **RDS parameter group** with customizable parameters (e.g., enabling connection logging).


Example usage:
```
module "database" {
  source = "The-Shy7/rds-instance-simple/aws"

  db_name = "example-db"
  security_group_ids = ["sg-12345678"]
  subnet_ids = ["subnet-12345678", "subnet-87654321"]
  credentials = {
    username = "dbadmin"
    password = "abc1+?_ahu"
  }
}
```