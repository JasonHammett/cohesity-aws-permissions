# Cohesity AWS Permissions

## Overview
This repo contains individual JSON files for Amazon Web Services (AWS) IAM user permissions that are required for specific cloud operations with Cohesity. 

The following Cohesity DataPlatform features are covered in this package:

* CloudArchive: Applies when using AWS S3 or Glacier for long term retention of backups.
* CloudSpin On-Demand: Applies when cloning Virtual Machines (VMs) to AWS.
* CloudSpin Policy Based (Full): Applies when using a Protection Policy to stage VMs in AWS.  Each backup contains a full copy of the VM (always full).
* CloudSpin Policy Based (Incremental): Applies when using a Protection Policy to stage VMs in AWS.  The first backup is full, with all subsequent backups being incremental (incremental forever).
* DataPlatform Cloud Edition Deployment: Applies when deploying DataPlatform Cloud Edition to AWS.
* Native Cloud Data Protection: Applies when backing up native AWS EC2 instances on Cohesity.

To limit permissions to a minimum, Cohesity uses the ability to attach an inline policy to an IAM user.  Users can also create a managed policy (AWS Console > IAM > Policies) for each of the capabilities listed above.

## Create and Assign Managed Policy
Managed (persistent) policies allow administrators to manage changes to policies in a single place across multiple users, with changing taking effect immediately and automatically.  This is preferred to inline policies which requires administrators to find users that have inline policies, and implement changes manually on an individual user basis.

To create a managed policy in AWS, do the following:

1.	Log into the AWS console.
2.	Click the Services menu item and select IAM from the list.
3.	Click on the Policies section.
4.	Click the JSON tab.
5.	Select all text within the policy editor.
6.	Copy and paste the appropriate JSON policy from one of the included JSON files in this package.
7.	Click the Review policy button.
8.	Enter an appropriate name for the policy in the Name field.
9.	Click the Create policy button.
10.	Click on Users section.
11.	Locate an click the user that will have the managed policy assigned.
12.	Click the Add permissions button.
13.	Click the Attach exsiting policies directly button.
14.	Search for your policy.  It is recommended that you include `Cohesity` or some other unique term in the policy names that makes searching for them easy.  Click the checkbox beside the appropriate policy.
15.	Click the Next: Review button.
16.	Click the Add permissions button.

## Assign Inline Policy
Each user can have an inline (one off) policy assigned directly.  This section covers assigning inline policies to AWS IAM users.  If you are using managed policies, you don't need to assign inline policies.

To assign an inline policy to an AWS IAM user, do the following:

1.	Log into the AWS console.
2.	Click the Services menu item and select IAM from the list.
3.	Click on the Users section.
4.	Locate an click the user that will have the inline policy assigned.
5.	Click the Add inline policy link.
6.	Click the JSON tab.
7.	Select all text within the policy editor.
8.	Copy and paste the appropriate JSON policy from one of the included JSON files in this package.
9.	Click the Review policy button.
10.	Enter an appropriate name for the policy in the Name field.
11.	Click the Create policy button.
