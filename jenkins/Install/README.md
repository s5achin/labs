# Manual Installation Steps 
### Install JAVA
```
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt-get update
sudo apt-get install -y fontconfig openjdk-17-jre openjdk-17-jdk
```
### Install Maven  ( on Jenkins machine )
```
wget https://archive.apache.org/dist/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
tar -xvzf apache-maven-3.9.6-bin.tar.gz
sudo mv apache-maven-3.9.6 /opt/maven
sudo nano /etc/profile.d/maven.sh

export MAVEN_HOME=/opt/maven
export PATH=$PATH:$MAVEN_HOME/bin (paste this inside file)
source /etc/profile.d/maven.sh (then load this)




````
### Install Jenkins
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

## `Below are Just FYI Only` 

##### how to restart Jenkins 
```
sudo systemctl restart jenkins  # to restart 
sudo systemctl stop jenkins     # to stop 
sudo systemctl start jenkins    # to start 
sudo systemctl status jenkins   # to check the status
```


##### Set JAVA_HOME & MAVEN_HOME as environment variables on Jenkins machine
```
sudo echo "MAVEN_HOME=\"/opt/apache-maven-3.8.5\"" >> /etc/profile
sudo echo "JAVA_HOME=\"/usr/lib/jvm/java-8-openjdk-amd64\"" >> /etc/profile 
sudo echo "PATH=\$JAVA_HOME/bin:\$MAVEN_HOME/bin:\$PATH" >> /etc/profile
source /etc/profile
```

