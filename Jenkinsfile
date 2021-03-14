pipeline {
   agent any

   tools {
      // Install the Maven version configured as "M3" and add it to the path. Demo comment
      maven "maven"
      jdk "java"
                
   }

   stages {
      stage('Code Checkout') {
         steps {
            // Get some code from a GitHub repository
            git branch: 'main', url: 'https://github.com/drvdevops2805/drv_multibranchPipejob_class9rev_repo.git'   
         }

      }
      
      
      stage('Code Testing') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn test"
         }
      }
         
          stage('Code Build') {
         steps {
           
            // To run Maven on a Windows agent, use
           bat "mvn package"
         }

      }
      
      stage('Code Deploy') {
         steps {
        
            // To run Maven on a Windows agent, use
           bat label: '', script: 'copy /Y target\\drvmultipipe-1.0.war F:\\apache-tomcat-9.0.16-windows-x64\\apache-tomcat-9.0.16\\webapps'
         }

      }
   }
}
