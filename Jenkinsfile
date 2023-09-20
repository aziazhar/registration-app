pipeline {
    agent any
    tools {
         jdk 'Java17'
         maven 'Maven3'
         git 'C:/Program Files/Git/git.exe'
  }
   stages{
   
      stage("Cleanup Workspace"){
          steps {
          cleanWs()     
     } 
   } 

    stage("Checkout from SCM"){
          steps {
             git branch: 'main', credentialsId: 'github', url: 'https://github.com/aziazhar/registration-app.git'
     } 
   } 

      stage("Build Application") {
          steps {
          sh "mvn clean package"
          }
             
     } 

        stage("Test Application") {
          steps {
          sh "mvn test"
          }
             
     } 
	 
    }

}
   
