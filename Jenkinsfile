pipeline {
    environment {
registry = "nainikapanguluri/java_app1"
registryCredential = 'dockerimage'
dockerImage = ''
}
    agent none
    stages {
        stage('Build') { 
            agent any
             steps {
                sh 'mvn install'
            }
            }
       
       stage ('dockerization') {
           agent any
            steps{
              script {
              dockerImage = docker.build("nainikapanguluri/java_app1")
                }
                 }
       }
       stage('Deploy Image') {
           agent any
          steps{
          script {
             docker.withRegistry( 'https://registry.hub.docker.com', 'dockerimage' ) {
                 dockerImage.push("${env.BUILD_NUMBER}")
                 dockerImage.push("latest")
      }
    }
  }
}    
                
             
        }
        
    }
