# Regex_webapp_AWS

## Overview
`Regex_webapp_AWS` is a web application designed to provide users with an interface to test and apply regular expressions. The application is hosted on AWS, leveraging its robust and scalable infrastructure. 

## Features
- **Interactive Regex Tester:** Users can input text and regex patterns to see real-time matches.
- **Pattern Library:** A collection of common regex patterns for various use cases.
- **Syntax Highlighting:** Enhanced readability with syntax highlighting for regex patterns and input text.
- **User Authentication:** Secure login and registration system using AWS Cognito.
- **Scalability:** Hosted on AWS with auto-scaling groups to handle varying loads.
- **Storage:** User data and patterns are stored securely using AWS RDS and S3.

## Architecture
The application follows a microservices architecture, using the following AWS services:
- **AWS EC2:** For hosting the web server.
- **AWS RDS:** For the relational database.
- **AWS S3:** For storing user data and files.
- **AWS Lambda:** For serverless functions to handle specific tasks.
- **AWS API Gateway:** For creating, publishing, maintaining, monitoring, and securing APIs.
- **AWS Cognito:** For user authentication and authorization.
- **AWS CloudFormation:** For deploying and managing the infrastructure.

## Getting Started

### Prerequisites
- AWS Account
- AWS CLI configured
- Docker (for local development)
- Node.js (for running the web application locally)

### Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/Regex_webapp_AWS.git
    cd Regex_webapp_AWS
    ```

2. **Install dependencies:**
    ```sh
    npm install
    ```

3. **Set up environment variables:**
    Create a `.env` file in the root directory and add the following:
    ```plaintext
    AWS_ACCESS_KEY_ID=your_access_key_id
    AWS_SECRET_ACCESS_KEY=your_secret_access_key
    AWS_REGION=your_aws_region
    COGNITO_USER_POOL_ID=your_user_pool_id
    COGNITO_APP_CLIENT_ID=your_app_client_id
    RDS_HOST=your_rds_host
    RDS_USER=your_rds_user
    RDS_PASSWORD=your_rds_password
    RDS_DB_NAME=your_db_name
    ```

4. **Run the application:**
    ```sh
    npm start
    ```

### Deployment

1. **Build the Docker image:**
    ```sh
    docker build -t regex_webapp .
    ```

2. **Push the Docker image to AWS ECR:**
    ```sh
    aws ecr create-repository --repository-name regex_webapp
    aws ecr get-login-password --region your_region | docker login --username AWS --password-stdin your_account_id.dkr.ecr.your_region.amazonaws.com
    docker tag regex_webapp:latest your_account_id.dkr.ecr.your_region.amazonaws.com/regex_webapp:latest
    docker push your_account_id.dkr.ecr.your_region.amazonaws.com/regex_webapp:latest
    ```

3. **Deploy using AWS CloudFormation:**
    ```sh
    aws cloudformation deploy --template-file cloudformation-template.yaml --stack-name RegexWebAppStack --capabilities CAPABILITY_NAMED_IAM
    ```

## Usage
- Access the web application at `http://your-aws-ec2-public-dns`.
- Register or log in using the authentication system.
- Start testing and applying regex patterns using the interactive interface.

## Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes.

## License
This project is licensed under the MIT License.

## Acknowledgments
- Thanks to the contributors of the libraries and tools used in this project.
- Special thanks to the AWS community for their comprehensive documentation and support.

