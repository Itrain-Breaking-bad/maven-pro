node {
   
   stage('Code Checkout') { // for display purposes
    git credentialsId: 'githubID', url: 'https://github.com/itrainpadman/maven-examples.git'  
   }
   stage('Code Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn clean compile'
    }  
   }
   stage('Test Run') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
     }  
   }
   stage('Code Quality') {
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn test'
       }
   } 
   stage('Archive to Jfrog') {
   } 
   stage('Docker Image') {
   } 
   stage('Deploy to Prods') {
   } 
}
