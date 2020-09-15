pipeline {
    environment {
registry = "nainikapanguluri/java_app"
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
              dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
                 }
       }
       stage('Deploy Image') {
           agent any
          steps{
          script {
             docker.withRegistry( '', registryCredential ) {
                dockerImage.push()
      }
    }
  }
}    
                
             
        }
        
    }
