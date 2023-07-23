# Docker_on_EC2
Docker Installation on AWS EC2 Instance
======================================

This README file provides step-by-step instructions on how to install Docker on an Amazon Web Services (AWS) Elastic Compute Cloud (EC2) instance. Docker allows you to run, deploy, and manage applications within containers, providing a lightweight and efficient way to package and distribute software.

Prerequisites
-------------
- An active AWS account with appropriate permissions to create and manage EC2 instances.
- Basic knowledge of working with AWS EC2 instances and SSH.
- An EC2 instance launched with an appropriate Linux-based Amazon Machine Image (AMI) (e.g., Ubuntu, Debian).

Installation Steps
------------------
1. Connect to the EC2 Instance:
   - Use an SSH client (e.g., OpenSSH) to connect to your EC2 instance using the public IP address or DNS name provided by AWS. Replace `username` with the appropriate username for your EC2 instance (e.g., "ubuntu" for Ubuntu-based instances).
     ```
     ssh -i /path/to/your/private-key.pem username@your-ec2-instance-public-ip
     ```

2. Transfer the Docker Installation Script:
   - Download the `install_docker.sh` script to your local machine from the repository.
   - Use SCP (Secure Copy Protocol) to transfer the `install_docker.sh` script to your EC2 instance. For example:
     ```
     scp -i /path/to/your/private-key.pem /path/to/install_docker.sh username@your-ec2-instance-public-ip:/path/to/destination/
     ```
   - Replace `/path/to/your/private-key.pem` with the path to your SSH private key and `/path/to/install_docker.sh` with the local path of the `install_docker.sh` script. Also, adjust the destination path on the EC2 instance according to your preference.

3. Execute the Docker Installation Script:
   - Connect to your EC2 instance (if not already connected).
   - Navigate to the directory where you transferred the `install_docker.sh` script.
   - Give the script execute permissions:
     ```
     chmod +x install_docker.sh
     ```
   - Run the script:
     ```
     ./install_docker.sh
     ```

4. Verify Docker Installation:
   - After the script completes successfully, Docker should be installed on your EC2 instance.
   - To check if Docker is installed and running correctly, you can run the following command:
     ```
     docker --version
     ```
   - This should display the Docker version installed on your EC2 instance.

Usage
-----
- With Docker installed on your EC2 instance, you can now use Docker to run and manage containers. For example, you can pull and run the official OS Docker image, host web applications, databases, and more.
- Before using Docker, ensure you have the appropriate Docker image you want to run and the necessary configurations for your specific use case.

Additional Notes
----------------
- Keep your system and Docker up to date with security patches and updates.
- Follow best security practices when working with Docker containers and exposing ports.


