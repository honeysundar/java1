pipeline {
    environment {
registry = "nainikapanguluri/java_app"
registryCredential = 'docker'

}
    agent none
    stages {
        stage('Build') { 
            agent any
             steps {
                sh 'mvn clean package'
        }
        }
       
       stage ('dockerization') {
           agent any
            steps{
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
       stage('Deploy Image') {
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
        
    }
