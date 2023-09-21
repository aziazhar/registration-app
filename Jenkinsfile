pipeline {
    agent {label 'Jenkins_Agent'}
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
             git branch: 'main', credentialsId: '', url: 'https://github.com/aziazhar/registration-app.git'
     } 
   } 

      stage("Build Application") {
          steps {
          bat "mvn clean package"
          }
             
     } 

        stage("Test Application") {
          steps {
          bat "mvn test"
          }
             
     } 
	 
    }

}
