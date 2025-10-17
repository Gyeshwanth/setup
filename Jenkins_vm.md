
## Server Setup

**EC2 Instances:**

* Create **EC2 instances** (Ubuntu 25.04, t2.medium)
* **Instance 1:** Jenkins Server
* 
* Configure **Security Groups** to allow ports:

  * Jenkins: 8080
  * SSH: 22
  * HTTP/HTTPS: 80, 443
* Connect to both instances using **MobaXterm** with the provided key pair.

---

## Jenkins Setup

1. **Install Java (Headless 21)**

   ```bash
   sudo apt update
   sudo apt install openjdk-21-jre-headless -y
   ```

2. **Install Jenkins (LTS version)**

   ```bash
   sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
     https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
   echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
   sudo apt update
   sudo apt install jenkins -y
   ```

3. **Access Jenkins UI**

   * Open: `http://<EC2_Public_IP>:8080`
   * Retrieve admin password:

     ```bash
     sudo cat /var/lib/jenkins/secrets/initialAdminPassword
     ```
   * Choose **Install Suggested Plugins** and create an admin user.

---
