# aws-project ( n.vir )👍😎

### Step-1

create vpc

 - name = tcs-vpc
 - ip = 20.20.0.0/16
 - enable DNS hostname

create subnet

 - pub-sn-1
 - az = 1a
 - ip = 20.20.1.0/24

 - pub-sn-2
 - az = 1b
 - ip = 20.20.2.0/24

create internet gateway  and attach to vpc

create security group

 - name =  tcs-sg
 - all traffic --> anywhere

create route table

 - rename main route table as  =  tcs-pub-rt
 - mention subnets and attach internet gateway
   

### Step-2

create RDS database

 - Standard create
 - Engine type  =  mysql
 - Templates  =  freetier
 - Master username  =  admin
 - Auto generate password
 - Virtual private cloud (VPC)  =  tcs-vpc
 - Public access  =  yes
 - Existing VPC security groups  = tcs-sg


### Step-3

create Dynamodb table

 - table name  =  employee_image_table
 - primary key  =  empid


### Step-4

create bucket

 - name  =  tcs-employee-bucket
 - versioning  =  enable


### Step-5

create EC2-instance

 - ami  =  ubuntu-22
 - instance types  =  t2.micro
 - subnet  =  based on rds ( subnet )
 - sg  =  tcs-sg
 - keypair  =  mykey.ppk


### Step-6

create IAM role

 - AWS service  =  ec2
 - Add permissions  =  AdministratorAccess
 - go to ec2 an attach this new role with instance
# For Ubuntu use:

```sh
sudo su -
apt-get update
apt-get install mysql-client -y
```
	   
For python and related frameworks

```sh
apt-get install python3
apt-get install python3-flask -y
apt-get install python3-pymysql
apt-get install python3-boto3 -y
```

For running application

```sh
python3 EmpApp.py
```
