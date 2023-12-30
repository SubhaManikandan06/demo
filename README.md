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

#### d. Enable firewall on port 8080 according to the instance used, if using azure vm or ec2 instance PORT 8080 need to be opened on the security group

#### e. Launch Jenkins

Once port openeded in local machine launch localhost:8080, if it any vm or ec2 intance [ipaddress]:8080

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/670cf89f-7a58-4119-a3dd-fbf505cad51f)

Get the password for admin by using the command 

**cat /var/lib/jenkins/secrets/initialAdminPassword**

And click on install the suggested plugins

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/f2969517-e04c-4f76-bb4a-0de984498682)

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/39aea69b-47cc-4570-a286-3f156fe1de8f)

Create username and password for your account and click continue

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/de93b83e-4e5b-46d1-b787-f676569b281b)

Once username is created you can see logged into jenkins with your account

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/bddce355-0e41-49d6-9981-82cc579dd787)

### STEP 2: Git integration with jenkins for private repo (public repo not needed)

#### a. Generate keypair.

Generate the public and private key in the jenkins installed server using command **ssh-keygen**
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/6e2aef4a-ee38-4937-9a3a-a5e724f91a6c)

#### b. Go to your GitHub repository and click on ‘Settings’ and Paste the public key.

Copy the public key from the terminal

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/5d5f19b5-30d4-4477-9530-a194890ba8fd)

And go the github settings as below images

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/bb2adba2-ceea-4d85-83a2-929cb25ae45d)

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/2e9b9be7-6b9d-4426-b526-1ab066f4d87a)

#### c. Add private key in jenkins

Manage Jenkins ---> Credentials
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/43c0f198-abc4-425e-bd64-383d0fb2bee3)

Click system
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/96f18af1-ed6e-4cf6-8ca0-e5c901342b06)

click Global Credentials
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/00bc66df-2d11-4863-a6e7-102b8387bcf9)

Add credetials
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/0ac707ae-40a7-43ba-8905-d86dba5bd1ae)

Get the private key from terminal

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/063c72b8-3a22-4508-8892-2e4c34d3fb28)

Follow the image to add private key

![image](https://github.com/SubhaManikandan06/demo/assets/84718563/b9cbe84f-b663-40d5-b53a-f16f7dacf5ae)

An id for it will be created 
![image](https://github.com/SubhaManikandan06/demo/assets/84718563/5028a177-ef96-4e5e-bf2b-3a6cc68a2896)











