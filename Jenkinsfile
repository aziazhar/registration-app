pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
         jdk 'Java17'
         maven 'Maven3'
  }
   stages{
      stage("Cleanup-Workspace"){
          steps {
          clearWs()     
     } 
   } 

    stage("Checkout from SCM"){
          steps {
            git branch: 'main', creditionals: 'github', url: 'https://github.com/Ashfaque-9x/register-app'
     } 
   } 

      stages('Build Application') {
          steps {
          sh "mvn clean package"
          }
             
     } 

        stages('Test Application') {
          steps {
          sh "mvn test"
          }
             
     } 


   } 

  }
}
