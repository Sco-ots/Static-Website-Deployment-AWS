## 1. Project Description

The goal of this project is to deploy a simple static website using Amazon S3 and AWS CloudFormation.
The infrastructure is defined as code using a CloudFormation YAML template. The website itself is uploaded to an S3 bucket.

## 2. Technologies and Services Used
-Amazon S3 <br />
-AWS CloudFormation <br />
-Git & GitHub <br />
-VS Code <br />
-YAML <br />
-cfn-lint <br />

## 3. Project Structure
text
Static-Website-Deployment-AWS/
│
├── cloudformation/
│   ├── static-website.yaml
│   └── .gitkeep
│
├── website/
│   ├── index.html
│   ├── error.html
│   └── .gitkeep
│
└── README.md

## 4. Implementation

### A. Creation of GitHub Repository

A repository was created on GitHub to host all the files and provide version control during the implementation process.

A clear and meaningful name was chosen for the repository, and an initial README was created.
After that, a dev branch was created.
Additionally, the planned folder structure was created with the cloudformation and website folders.


### B. Simple HTML Page

A simple HTML page for testing and proof-of-concept purposes was created. It contains a page title, text, and the author's name.

Only the most necessary content was included in the HTML file.
After that, the functionality of the HTML page was tested in a local web browser.
Additionaly and error.html page was created to satisfy the layout of the CloudFormation Template from the offical documentation described in Step C.


### C. CloudFormation Template

With the help of the CloudFormation documentation, a CloudFormation template was created using the YAML file format.

According to the project requirements, it was especially important to ensure public access and disable the use of ACLs.
To achieve this, the following changes were made to the template taken from the documentation:
Setting the IgnorePublicAcls and BlockPublicAcls boolean values to true.
Adding the ObjectOwnership: BucketOwnerEnforced rule under OwnershipControls.

Once the template was complete, it was validated using cfn-lint to check for potential errors.


### D. Deploying the CloudFormation Stack

The AWS Management Console was used to deploy the template. A new stack was created, and the YAML file was uploaded.
After the deployment was finished, the stack events were checked to ensure that no errors occurred.

Steps:

1.Open AWS CloudFormation.
2.Select Create Stack.
3.Upload the static-website.yaml template.
4.Enter the stack name static-website-stack.
5.Review the configuration and create the stack.
6.Check the stack events to verify successful deployment.


### E. Uploading HTML Files to the S3 Bucket

The website files were uploaded to the S3 bucket created by CloudFormation.
Files uploaded:

-index.html
-error.html


### F. Testing the Website

The website URL was retrieved from the CloudFormation stack outputs.
The S3 website endpoint was opened in a browser to verify that the website was accessible and that the HTML page loaded correctly.


### G. Result

The CloudFormation stack was deployed successfully.

You can visit the website here:
http://static-website-stack-s3bucket-c7dtr4rynfbg.s3-website-us-east-1.amazonaws.com
