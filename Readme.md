# Lambda Email Service

## Overview

Lambda Email Service is a secure and efficient solution for handling email operations using Amazon Web Services (AWS). The service is built on AWS Lambda, a serverless computing service that runs code in response to events and automatically manages underlying compute resources. Triggered via the AWS API Gateway, it provides a robust and scalable platform for email operations.

## Key Features

- **AWS Lambda Integration**: The service runs as an AWS Lambda function, leveraging the scalability and cost-effectiveness of serverless computing.

- **AWS API Gateway**: The AWS API Gateway triggers the Lambda function, acting as a front door for incoming requests.

- **Data Security with AWS SSM**: All sensitive information, such as secrets, are securely stored in the AWS Systems Manager Parameter Store (SSM), ensuring data privacy and security.

- **Robust Email Operations**: The service processes user details and sends emails efficiently, providing a reliable solution for email operations.

- **Exception Handling**: The service includes mechanisms to handle exceptions, ensuring robust and reliable operations.

## Code Structure

The core of the service is the `Function` class, which includes a method, `FunctionHandler`, designed to handle incoming user details and send emails accordingly. User details are extracted from the query string parameters of the `APIGatewayProxyRequest` object. 

To ensure data security, the service retrieves the sender's email, name, and password from the AWS SSM. This is facilitated by the `getOwnerDetails` and `getValuefromSSM` methods.

The `MyObject` class is used to model user details, providing a structured way to handle and process user information.

## Getting Started

To get started with the Lambda Email Service, clone the repository and follow the setup instructions in the 'Installation' section.
## Installation

This project is built with .NET Core and runs as an AWS Lambda function. It uses GitHub Actions for continuous deployment. Here are the steps to install and run the project:

1. **Prerequisites**: Ensure you have the following installed on your local machine:
    - [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)
    - [AWS CLI](https://aws.amazon.com/cli/)

2. **Clone the Repository**: Clone this repository to your local machine using the following command:
    ```bash
    git clone https://github.com/BivekKumarMali/Lamdha-Email-Service.git
    ```

3. **Build the Project**: Navigate to the project directory and build the project using the .NET CLI:
    ```bash
    cd Lamdha-Email-Service
    dotnet build
    ```

4. **Configure GitHub Actions**: This project uses GitHub Actions for continuous deployment. Make sure to set up the necessary secrets in your repository settings for AWS credentials (`AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`), AWS region (`AWS_REGION`), and other necessary parameters. Check the `.github/workflows` directory to understand the workflow file.

5. **Push Changes**: After making changes, push them to your repository. GitHub Actions will automatically deploy your function to AWS Lambda.

6. **Test the Function**: After deployment, you can test the function through the AWS Lambda console or the AWS API Gateway.

Remember to configure the necessary permissions and roles in your AWS account for Lambda execution and API Gateway invocation.

