📘 Project README – CI/CD Static Website Deployment on AWS
🚀 Project Overview
This project demonstrates a complete CI/CD pipeline using Jenkins to deploy a static website on AWS EC2 (Ubuntu) with Apache web server.
The goal was to automate code integration and deployment while handling real-world issues like repository mismatches, file path errors, and branch changes.

🧰 Tech Stack


Cloud: AWS EC2


Web Server: Apache (HTTPD)


CI/CD Tool: Jenkins


Version Control: Git & GitHub


OS: Ubuntu


Networking: Elastic IP



⚙️ Architecture


Developer pushes code to GitHub


Jenkins pulls latest code (CI)


Jenkins builds & deploys to EC2 (CD)


Apache serves the website



🔧 Setup Steps
1. EC2 Instance Setup


Launch Ubuntu EC2 instance


Allow ports:


22 (SSH)


80 (HTTP)




Install Apache:


sudo apt updatesudo apt install apache2 -y

2. Jenkins Setup


Install Jenkins on server


Configure:


GitHub repository


Credentials




Create:


Freestyle job (CI)


Pipeline job (CD)





3. CI Pipeline (Freestyle Job)


Pull code from GitHub


Validate repository connection


Handle branch updates (master → main)



4. CD Pipeline (Jenkinsfile)
Example pipeline:
pipeline {    agent any    stages {        stage('Clone Repo') {            steps {                git 'https://github.com/your-repo.git'            }        }        stage('Deploy') {            steps {                sh 'sudo cp -r * /var/www/html/'            }        }    }}

5. Elastic IP Configuration


Attach Elastic IP to EC2


Ensures stable public access



🌐 Access the Website
Open browser:
http://<Elastic-IP>

🧠 Challenges Faced


Repository mismatch issues


File path and naming errors


Branch change (master → main)


Deployment permission issues



✅ Key Learnings


CI/CD pipeline basics using Jenkins


AWS EC2 setup and configuration


Debugging real deployment errors


Importance of stable IP using Elastic IP



📌 Future Improvements


Add domain using Route 53


Implement HTTPS using SSL


Automate using Docker


Use Terraform for infrastructure



👨‍💻 Author
Muthu Pandian

