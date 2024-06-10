# pearl_assignment
A simple Nodejs app deployed on AWS EC2 using terraform, kubernetes, docker, Github

# Deployment Steps on AWS EC2
Launch an EC2 Instance:

Launch an EC2 instance using Amazon Linux 2 AMI.
Ensure security groups allow HTTP (port 80) and SSH (port 22) access.

# Install Docker
sudo yum update -y
sudo amazon-linux-extras install docker
sudo service docker start
sudo usermod -a -G docker ec2-user

# Clone the Repository:
git clone "your-git-repo-url"
cd "your-repo"

# Build and Run Docker Container:
docker build -t pearl_assign .
docker run -d -p 80:3000 pearl_assign

# Access the Application:
Open a browser and navigate to the public IP of your EC2 instance.

# Deployment Steps:
Install terraform
cd terraform
terraform init
terraform apply

Install kubernetes
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
