pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
         jdk 'Java17'
         maven 'Maven3'
         git 'C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Git'
  }
   stages{
   
      stage("Cleanup Workspace"){
          steps {
          clearWs()     
     } 
   } 

    stage("Checkout from SCM"){
          steps {
            git branch: 'main', creditionalsId: 'github', url: 'https://github.com/aziazhar/register-app'
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
