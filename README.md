# Project Documentation for Karatu Exam

## Project Overview
This project involves provisioning a Linux server, installing a web server, deploying a simple HTML landing page, and configuring network settings to showcase your team’s capabilities. This serves as a prototype for a web application aimed at impressing potential investors.

---

## Setup Instructions

### 1. Provisioning the Server
1. Log in to your AWS Management Console.
2. Navigate to the EC2 dashboard and click on **Launch Instance**.
3. Choose **Ubuntu Server 20.04 LTS** as the AMI.
4. Select an appropriate instance type (e.g., `t2.micro`).
5. Configure security group rules to allow:
   - SSH traffic on port 22.
   - HTTP traffic on port 80.
6. Launch the instance and download the private key file (`.pem`).
7. Note the public IP address of the instance.

### 2. SSH into the Server
1. Open a terminal on your local machine.
2. Navigate to the directory containing the `.pem` file.
3. Run the command:
   ```bash
   ssh -i "<your-key>.pem" ubuntu@<Public_IP_Address>
   ```
4. Replace `<your-key>` with the name of your `.pem` file and `<Public_IP_Address>` with the instance’s public IP.

### 3. Install Apache
1. Update the server packages:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Install Apache:
   ```bash
   sudo apt install apache2 -y
   ```
3. Verify Apache installation by visiting `http://<Public_IP_Address>` in your browser.

### 4. Deploy the HTML Page
1. Navigate to the web server's root directory:
   ```bash
   cd /var/www/html
   ```
2. Remove the default index.html file:
   ```bash
   sudo rm index.html
   ```
3. Create your own HTML page:
   ```bash
   sudo nano index.html
   ```
4. Add the following content to `index.html`:
   ```html
   <!DOCTYPE html>
   <html>
   <head>
       <title>Welcome to [Your Name] Landing Page</title>
   </head>
   <body>
       <h1>Welcome to [Your Name] Landing Page</h1>
       <h2>About Me</h2>
   </body>
   </html>
   ```
5. Save and close the file.

### 5. Configure Security Groups for HTTP Traffic
1. Go to the EC2 dashboard on AWS.
2. Edit the security group for your instance.
3. Ensure there is a rule to allow HTTP traffic on port 80 from anywhere (0.0.0.0/0).
4. Save the changes.

### 6. Test the Landing Page
1. Open your browser.
2. Visit `http://<Public_IP_Address>` to view your landing page.

---

## Public IP Address
Public IP Address: `http://13.53.78.143/`

---

## Useful Information
- **Credentials:** Use the `AltSchool-pair.pem` file for SSH access.
- **Web Server Root Directory:** `/var/www/html`
- **Default Port for HTTP Traffic:** 80

---

## Screenshots
1. **AWS EC2 Instance Running:** Screenshot of the EC2 dashboard.
2. **SSH Connection:** Screenshot of the terminal after connecting via SSH.
3. **Apache Installation:** Screenshot of the terminal showing Apache installation.
4. **Landing Page:** Screenshot of the browser displaying the deployed landing page.

Ensure all screenshots are added to the repository for validation.

---

## Repository Structure
```
.
├── README.md
├── index.html
└── screenshots/
    ├── ec2_instance_running.png
    ├── ssh_connection.png
    ├── apache_installation.png
    └── landing_page.png
```

---

