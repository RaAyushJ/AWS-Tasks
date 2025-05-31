# AWS TASKS – Ayush Raj (22BRS1117)

This repository contains a series of AWS-based lab experiments completed as part of academic coursework. Each experiment explores and demonstrates various AWS services, their configuration, and real-world application.

---

Contents

- [Experiment 1: EC2 Instance Creation and Flask App Deployment]
- [Experiment 2: Auto Scaling with Launch Template and AMI]
- [Experiment 3: IAM Role & Policy Creation using JSON]
- [Experiment 4: Static Website Hosting using Amazon S3]
- [Experiment 5: RDS Database Creation & Migration]

---

## Experiment 1: EC2 Instance Creation and Flask App Deployment

- Created an EC2 instance using AWS Free Tier (`t2.micro`)
- Converted key pair to `.ppk` format for PuTTY
- Connected to the instance and installed dependencies
- Created and deployed a simple Flask application:```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
    Verified that the Flask app was accessible via the public IP.


## Experiment 2: Auto Scaling with Launch Template and AMI

    Created an AMI from a running EC2 instance.

    Created a launch template using the AMI.

    Set up an Auto Scaling Group with:

        Subnet and VPC configuration

        Health check and scaling policies

        Group metrics enabled

    Verified that auto scaling was functional.

## Experiment 3: IAM Role & Policy Creation using JSON

    Created a custom policy in JSON format to allow starting and stopping of EC2 instances:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances",
        "ec2:StartInstances",
        "ec2:StopInstances",
        "ec2:RebootInstances"
      ],
      "Resource": "*"
    }
  ]
}

    Attached the policy to a user and verified access.

    Later modified the policy to deny starting instances while allowing descriptions.

## Experiment 4: Static Website Hosting using Amazon S3

    Created an S3 bucket and uploaded an HTML file.

    Enabled static website hosting in bucket properties.

    Configured public access by:

        Disabling "Block all public access"

        Enabling ACLs

        Making objects public

    Website was successfully hosted and accessible via the S3 link.

## Experiment 5: RDS Database Creation and Migration

    Created an Amazon RDS instance with required configurations.

    Configured storage, networking, security group, and key management settings.

    Used AWS DMS to migrate an existing database:

        Created data collector

        Initiated and verified migration process

Files Included

    PDF documentation for each experiment

    .ppk key file for EC2 instance connection (Exp1.ppk)

Author

Ayush Raj








