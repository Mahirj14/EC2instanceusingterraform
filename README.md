# EC2instanceusingterraform


Create a new directory for your Terraform project and create a new file named main.tf inside it.

Add the following code to main.tf to configure the AWS provider and define the EC2 instance resource:


provider "aws" {
  region = "us-east-1" # change this to your desired region
}

resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0" # change this to your desired AMI ID
  instance_type = "t2.micro" # change this to your desired instance type
  key_name      = "my-key-pair" # change this to your desired key pair name

  tags = {
    Name = "example-instance"
  }
}
