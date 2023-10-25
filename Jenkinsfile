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


        stage("SonarQube Analysis") {
          steps {
             script {
		  withSonarQubeEnv(credentialsId: 'jenkins-sonarqube-token') {
		  sh "mvn sonar:sonar"
	            }
	        }
          }
             
     } 
	
 //      stage('Sonarqube Analysis') {
 //            steps {
 //                sh ''' $SCANNER_HOME/bin/sonar-scanner \
 //                -Dsonar.host.url=http://13.235.103.113:9000// \
 //                -Dsonar.login=squ_0398341302b5dedd04cef8168ff1bc627b010fb3 \
 //                -Dsonar.projectName=shopping-cart \
 //                -Dsonar.java.binaries=. \
 //                -Dsonar.projectKey=shopping-cart '''
 //            }
 //        }
	
	// stage("Build Application") {
 //          steps {
 //          sh"mvn package -DskipTests"
 //          }
             
 //     }
	 
    }

}
