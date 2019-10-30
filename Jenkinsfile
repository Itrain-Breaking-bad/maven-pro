node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubid', url: 'https://github.com/Itrain-Breaking-bad/maven-pro.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'jJDK-1.8', maven: 'Maven3.6') {
     sh 'mvn clean compile'
    }  
   }
   stage('Unit Test') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6') {
        sh 'mvn test'
     }  
   }
   stage('SonarQube Analysis') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven3.6') {
       sh 'mvn sonar:sonar \
        -Dsonar.projectKey=maven-pro-sanoop \
        -Dsonar.organization=sanoop \
  	     -Dsonar.host.url=https://sonarcloud.io \
  	     -Dsonar.login=5a858a56ebc8d9140fae5633e34dc2c4e5f4a4d3 '
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
