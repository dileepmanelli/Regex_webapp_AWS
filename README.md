# Regex_webapp_AWS

## Overview
`Regex_webapp_AWS` is a web application built with Flask, designed for testing and applying regular expressions. The application is deployed on AWS using EC2, providing a scalable and robust environment.

## Features
- **Interactive Regex Tester:** Real-time testing of regex patterns against input text.
- **Pattern Library:** Collection of common regex patterns for various use cases.
- **Syntax Highlighting:** Enhanced readability with syntax highlighting.
- **User Authentication:** Secure user login and registration.
- **Scalability:** Deployed on AWS EC2 to handle varying loads.

## Architecture
The application architecture includes:
- **Flask:** For the web application framework.
- **AWS EC2:** For hosting the web application.
- **AWS RDS (Optional):** For relational database storage.
- **AWS S3 (Optional):** For storing user data and files.

## Getting Started

### Prerequisites
- AWS Account
- AWS CLI configured
- Python 3.x
- Virtualenv

### Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/yourusername/Regex_webapp_AWS.git
    cd Regex_webapp_AWS
    ```

2. **Create a virtual environment and activate it:**
    ```sh
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install dependencies:**
    ```sh
    pip install -r requirements.txt
    ```

4. **Set up environment variables:**
    Create a `.env` file in the root directory and add the following:
    ```plaintext
    FLASK_APP=app.py
    FLASK_ENV=development
    SECRET_KEY=your_secret_key
    AWS_ACCESS_KEY_ID=your_access_key_id
    AWS_SECRET_ACCESS_KEY=your_secret_access_key
    AWS_REGION=your_aws_region
    ```

5. **Run the application locally:**
    ```sh
    flask run
    ```

### Deployment

1. **Create an EC2 instance:**
    - Launch an EC2 instance from the AWS Management Console.
    - Choose an appropriate Amazon Machine Image (AMI).
    - Configure security groups to allow HTTP (port 80) and SSH (port 22) access.

2. **SSH into your EC2 instance:**
    ```sh
    ssh -i your-key-pair.pem ec2-user@your-ec2-public-dns
    ```

3. **Install dependencies on EC2:**
    ```sh
    sudo yum update -y
    sudo yum install -y python3
    sudo pip3 install virtualenv
    ```

4. **Transfer your application to EC2:**
    ```sh
    scp -i your-key-pair.pem -r * ec2-user@your-ec2-public-dns:/home/ec2-user/Regex_webapp_AWS
    ```

5. **Set up the application on EC2:**
    ```sh
    cd Regex_webapp_AWS
    python3 -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    ```

6. **Run the application on EC2:**
    ```sh
    nohup flask run --host=0.0.0.0 &
    ```

7. **Access your application:**
    - Open a browser and navigate to `http://your-ec2-public-dns`.

## Usage
- Access the web application at `http://your-ec2-public-dns`.
- Register or log in using the authentication system.
- Start testing and applying regex patterns using the interactive interface.

## Contributing
Contributions are welcome! Please fork the repository and create a pull request with your changes.




