# Creating-AWS-Resources-with-Functions-and-Arrays-Using-Shell-Scripting 

This project will begin by creating two functions:

1. One for provisioning EC2 Instances and 

2. Another for Setting up S3 buckets 

This functions will streamline the process of resource creation and enable us to automate task effectively

## Function to Provision AWS EC2 Instances 

To programatically create EC2 instances, you must use the [Official Documentation](https://docs.aws.amazon.com/cli/latest/reference/ec2/) to understand how to use the ['aws cli' to create instances](https://docs.aws.amazon.com/cli/latest/reference/ec2/) 

From the Available Commands, you will be able to interact with AWS programmatically. 

![Official Documentation](./img/01.%20Official%20Documentation.png) 

If you search for **run-instances** on the page with **Control F** on your keyboard, click on it, and it will take you to the detailed documentation on the sub-command to create EC2 instances. 

Here is an example of how to create EC2 instances using the command line. 

![How to Create EC2 Instances](./img/03.%20How%20to%20Create%20EC2%20Instances.png)

**Note:** Make sure you have a key pair created in aws console. That can replace **'MyKeyPair'** with your key name. 

On the same page of official documentation, if you search for one of the arguments, you will be able to read more about how to pass different arguments to the cli. 

For the command to work: A key pair must already exist. You must create a key pair.

1. Navigate to the AWS EC2 console.

2. Create a key pair or use existing one. 

![Create Keypair on the Console](./img/04.%20Create%20Keypair%20on%20the%20Console.png) 

Now, let's update the shell script and create the function that will be responsible for creating EC2 instances. 

![05. Creating EC2 Instance](./img/05.%20Creating%20EC2%20Instaance.png) 

![06. Creating EC2 Instance Cont](./img/06.%20Creating%20EC2%20Instaance%20Cont.png) 

Highlighting some new areas 

- **$?:** This is a special variable that holds the exit status of the last executed command. In this case, it checks if the aws ec2 run-instances command was successful. Exit status that equals "0", then echo the message to confirm that the previous command was successful. 

- We have once again used environment variables to hold the value of **ami_id, count region** and replaced with their respective values with **ami_id, count and region** 

## Define Function to Create S3 Buckets and Learn about Arrays 

Before diving into creating S3 buckets, it's beneficial to brush up AWS S3 bucket concepts. 

The [AWS CLI reference for S3 can be found here]() We will be using it in the script. 
 
In thi