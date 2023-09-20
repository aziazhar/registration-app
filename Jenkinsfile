pipeline {
    agent { label 'Agent-Jenkins' }
    tools {
         jdk 'Java17'
         maven 'Maven3'
  }
   stages{
   
      stage("Cleanup Workspace"){
          steps {
          clearWs()     
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
