# EC2instanceusingterraform





first you have to configure AWS CLI in your system

```
➜ ~ aws configure
AWS Access Key ID [None]: AKIA****************
AWS Secret Access Key [None]: kkQEi=********************
Default region name [None]: us-east-1
Default output format [None]:

```
 * this means you connected with your aws console.
 
 
 
* Create a new directory for Terraform  and create a new file named main.tf inside it.

* Add the following code to main.tf to configure the AWS provider and define the EC2 instance resource:


```
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro" 
  key_name      = "my-key-pair" 

  tags = {
    Name = "example-instance"
  }
}
```


* Initialize your Terraform project by running terraform init
* Create an execution plan by running terraform plan
* Apply the changes by running terraform apply. This will create the EC2 instance.
* Verify that the EC2 instance was created by logging in to the AWS console or by running terraform show to view the current state of your infrastructure





* you can check also like using this command for perticuler instance id

```
aws ec2 describe-instances – instance-ids i-12345*****
```
