

## Server Setup

**EC2 Instances:**

* Create **EC2 instances** (Ubuntu 25.04, t2.medium)
* **Instance :** SonarQube Server
* Configure **Security Groups** to allow ports:

  * SonarQube: 9000
  * SSH: 22
  * HTTP/HTTPS: 80, 443
* Connect to both instances using **MobaXterm** with the provided key pair.



## SonarQube Setup (Docker)

1. **Install Docker**

   ```bash
   sudo apt update
   sudo apt install docker.io -y
   sudo usermod -aG docker ubuntu
   exit
   ```

2. **Run SonarQube Container**

   ```bash
   sudo docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
   ```

3. **Verify Setup**

   ```bash
   docker images
   docker ps
   ```

4. **Access SonarQube Dashboard:**

   * URL: `http://<EC2_Public_IP>:9000`
   * Default credentials: `admin / admin`
   * Change password to a secure one (e.g., `admin / java`).




