pipeline {
    agent any
    tools {
         jdk 'Java17'
         maven 'Maven3'
        
  }
   stages{
   
      stage("Cleanup Workspace"){
          steps {
          cleanWs()     
     } 
   } 

    stage("Checkout from SCM"){
          steps {
             git branch: 'main', credentialsId: '', url: 'https://github.com/aziazhar/registration-app'
     } 
   } 

      stage("Build Application") {
          steps {
          sh"mvn clean package"
          }
             
     } 

        stage("Test Application") {
          steps {
          sh"mvn test"
          }
             
     } 
	 
    }

}
