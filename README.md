# demo
## Jenkins setup
### STEP 1: Jenkins Installation on Linux
#### a. Install Java on the system 

I am installing the latest version of java

**sudo apt update**

**sudo apt install fontconfig openjdk-17-jre**

java -version

output:

openjdk version "17.0.8" 2023-07-18

OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)

OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)

#### b. Install Jenkins 

First, add the repository key to your system:

**sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key**

**Next, let’s append the Debian package repository address to the server’s sources.list:**
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
sudo apt-get update

sudo apt-get install jenkins

#### c. Start Jenkins 

Start the jenkins

**systemctl start jenkins**

And then check the status to verify jenkins is working or not.

**systemctl status jenkins**

#### d. Enable firewall on port 8080 according to the instance used, if using azure vm or ec2 instance PORT 8080 need to be opened

#### e. Launch Jenkins

Once port openeded in local machine launch localhost:8080, if it any vm or ec2 intance [ipaddress]:8080

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/670cf89f-7a58-4119-a3dd-fbf505cad51f)

Get the password for admin by using the command 

**cat /var/lib/jenkins/secrets/initialAdminPassword**

And click on install the suggested plugins

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/f2969517-e04c-4f76-bb4a-0de984498682)


