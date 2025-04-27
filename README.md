
This project demonstrates a complete end-to-end **DevOps pipeline** with automation for continuous integration and continuous deployment (CI/CD) to AWS. The pipeline automates the following tasks:

- **Code Commit**: Push code to GitHub repository.
- **Build**: Use AWS CodeBuild to compile, test, and build the application.
- **Test**: Automated testing with AWS CodeBuild.
- **Deploy**: Use AWS CodePipeline for automating deployment to **EC2** instances or other AWS services.
- **Monitoring and Logging**: Integration with AWS CloudWatch for monitoring the pipeline stages and logging the build and deployment processes.

## Architecture

The pipeline is built with the following architecture components:

- **AWS CodeCommit**: Source control to manage the source code (alternative to GitHub if required).
- **AWS CodeBuild**: Builds the application and runs tests.
- **AWS CodePipeline**: Automates the build, test, and deploy process.
- **AWS EC2**: Hosts the application (for deployment).
- **IAM Roles**: Ensures proper permissions for each AWS service.

 Prerequisites

Before you begin, ensure you have the following:

- An **AWS Account** with the necessary permissions.
- **AWS CLI** installed and configured.
- **GitHub Repository** (if using GitHub for version control).
- **AWS IAM Roles** for CodeBuild, CodePipeline, and EC2 setup.

## Setup and Configuration

Follow the steps below to set up your AWS DevOps pipeline.

### 1. Clone the Repository
Clone this repository to your local machine:

```bash
git clone https://github.com/jangadivya18/AWS-Project.git

2. AWS Configuration
Ensure your AWS CLI is configured with the correct credentials:

bash
Copy
Edit
aws configure

3. Create AWS Resources
Create the required IAM roles and EC2 instances through AWS Management Console or using CloudFormation templates in this repository. The resources are defined in the infrastructure/ folder.

a. EC2 Setup
Follow the instructions in the infrastructure/EC2_Setup.md file to configure an EC2 instance.

b. CodePipeline Setup
Configure AWS CodePipeline to connect your GitHub repository with CodeBuild for the CI/CD pipeline. This can be done using the pipeline.yaml configuration file or the AWS Console.

4. Configure AWS CodeBuild
In AWS CodeBuild, set up the build specification (buildspec.yml) that defines the build commands.

5. Deploy to EC2
Once the pipeline is set up, CodePipeline will automatically deploy the built artifacts to your EC2 instances.

How to Use the Pipeline
Push Changes to GitHub: Whenever you push changes to the GitHub repository, the pipeline is triggered automatically.

CI/CD Pipeline: The pipeline will fetch the code from GitHub, build the application, and deploy it to the EC2 instance.
