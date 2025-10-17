## Gitleaks Setup

1. **Download Latest Version**

   ```bash
   GITLEAKS_VERSION=$(curl -s "https://api.github.com/repos/gitleaks/gitleaks/releases/latest" | grep -Po '"tag_name": "v\\K[0-9.]+')
   wget -qO gitleaks.tar.gz https://github.com/gitleaks/gitleaks/releases/latest/download/gitleaks_${GITLEAKS_VERSION}_linux_x64.tar.gz
   ```

2. **Install and Verify**

   ```bash
   sudo tar xf gitleaks.tar.gz -C /usr/local/bin gitleaks
   gitleaks version
   rm -rf gitleaks.tar.gz
   ```

---

## Trivy Setup

1. **Install Trivy**

   ```bash
   sudo apt-get install wget apt-transport-https gnupg lsb-release -y
   wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
   echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee -a /etc/apt/sources.list.d/trivy.list
   sudo apt-get update
   sudo apt-get install trivy -y
   ```

2. **Check Version**

   ```bash
   trivy --version
   ```

---
