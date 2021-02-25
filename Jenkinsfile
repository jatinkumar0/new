[10:30 PM] Shashi Kumar Singh
    
pipeline {​​​​​​​
 
agent any
 
tools {​​​​​​​
 
maven 'maven'
 
}​​​​​​​
 
stages {​​​​​​​
 
stage('Git Checkout') {​​​​​​​
 
steps {​​​​​​​
 
git branch: 'main',
 
credentialsId: '14bc8520-e78c-483f-b2ee-f33b97c9b843',
 
url: 'https://github.com/shashisingh1998/new.git'
 
}​​​​​​​
 
}​​​​​​​
 
stage ('Clean') {​​​​​​​
 
steps {​​​​​​​
 
sh 'mvn clean'
 
}​​​​​​​
 
}​​​​​​​
 
stage ('Compile') {​​​​​​​
 
steps {​​​​​​​
 
sh 'mvn compile'
 
}​​​​​​​
 
}​​​​​​​
 
stage('Test') {​​​​​​​
 
steps {​​​​​​​
 
sh 'mvn test'
 
}​​​​​​​
 
post {​​​​​​​
 
always {​​​​​​​
 
junit '**/target/surefire-reports/*.xml'
 
}​​​​​​​
 
}​​​​​​​
 
}​​​​​​​
 
stage ('Package') {​​​​​​​
 
steps {​​​​​​​
 
sh 'mvn package'
 
}​​​​​​​
 
}​​​​​​​
 
stage ('Deploy War File') {​​​​​​​
 
steps {​​​​​​​
 
sh "cp target/game-of-life.war /home/ec2-user/apache-tomcat-8.5.61/webapps/"
 
}​​​​​​​
 
}​​​​​​​
 
stage ('Restart tomcat') {​​​​​​​
 
steps {​​​​​​​
 
sh "/apache-tomcat-8.5.61/bin/shutdown.sh"
 
sh "/apache-tomcat-8.5.61/bin/startup.sh"
 
}​​​​​​​
 
}​​​​​​​
 
}​​​​​​​
 
}​​​​​​​
