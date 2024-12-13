Cloud Security with AWS IAM 


In this project, we are setting up a secure and efficient AWS environment for NextWork, focusing on the development and management of AWS resources. The goal is to onboard an intern, giving them controlled access to a development EC2 instance while ensuring they don’t interfere with the production environment. We will use AWS services like EC2 for hosting instances and IAM (Identity and Access Management) for managing user permissions and access control.

AWS Services Used:

EC2 (Elastic Compute Cloud):
EC2 provides scalable computing capacity in the cloud. In this project, we deploy two EC2 instances—one for the production environment and one for development. The intern will be granted access only to the development instance to ensure that their actions don't impact the production environment.

IAM (Identity and Access Management):
IAM enables us to securely control access to AWS services and resources. Through IAM, we create policies, user groups, and users to manage permissions. This ensures that the intern can access only the development EC2 instance, with no access to the production instance, thus minimizing security risks.

Instructions:

Create an IAM Policy:
We start by creating an IAM policy that grants the intern access to the development EC2 instance, while restricting access to the production instance. The policy will allow actions like starting, stopping, and describing the development instance, but will deny actions such as creating or deleting tags.
Create an AWS Account Alias:
To make it easier for the intern to log into the AWS console, we create an AWS account alias. This provides a user-friendly sign-in URL for the intern, making it simpler to access the AWS Management Console.
Create IAM User Groups and Users:
We set up a dedicated IAM user group, "nextwork-dev-group," and assign the permissions related to the development environment to this group. Then, we create a new IAM user for the intern, associating them with this group to ensure they have the correct permissions.
Test the Intern’s Access:
After setting up the intern’s user account and permissions, we log in as the intern using the IAM credentials. We test access to both the development and production EC2 instances to ensure the intern only has the expected permissions for the development instance.
Verify Access Restrictions:
Finally, we test the intern’s ability to perform actions on the EC2 instances. We attempt to stop both the production and development instances. The intern should be unable to stop the production instance, but will be able to stop the development instance, confirming that the permissions are set correctly.
