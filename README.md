# jenkins
<img src=j1.jpg>
<img src=j2.png>

## jenkins installation in ubuntu

Jenkins Debian Packages
This is the Debian package repository of Jenkins to automate installation and upgrade. To use this repository, first add the key to your system:

 ```   
  sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
 ``` 
Then add a Jenkins apt repository entry:
 ```   
  echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
```  
Update your local package index, then finally install Jenkins:

 ```  
  sudo apt-get update
  sudo apt-get install fontconfig openjdk-17-jre
  sudo apt-get install jenkins
```
### URL
http://IPAdress:8080


<img src=j3.png>
