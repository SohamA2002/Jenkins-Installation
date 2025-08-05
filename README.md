# Jenkins-Installation

## 1. Enable Instance with AWS and connect to instance via ssh or connect instance.

### 2. Installation of Java and Jenkins
* First, update the default Ubuntu packages lists for upgrades with the following command:
```bash
sudo apt-get update
```

* Install Java
```bash
sudo apt install fontconfig openjdk-21-jre
java -version
```

* Install Jenkins
```bash
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

* Start Jenkins
```
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
```

3. With Jenkins installed, we can proceed with adjusting the firewall settings. By default, Jenkins will run on port 8080.

* In order to ensure that this port is accessible, we will need to configure the built-in Ubuntu firewall (ufw). To open the 8080 port and enable the firewall, use the following commands:
```
sudo ufw allow 8080
```
```
sudo ufw enable
```
* Once done, test whether the firewall is active using this command:
```
sudo ufw status
```


