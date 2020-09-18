pipeline {
    agent any
    environment {
registry = "nainikapanguluri/java_app1"
registryCredential = 'docker-hub'
dockerImage = ''
}
    agent none
    stages {
        stage('Build') { 
            
             steps {
                sh 'mvn install'
            }
            }
       
       stage ('dockerization') {
           
            steps{
              script {
              dockerImage = docker.build("nainikapanguluri/java_app1")
                }
                 }
       }
       stage('Deploy Image') {
           
          steps{
          script {
              withDockerRegistry([ credentialsId: "docker-hub", url: "https://registry.hub.docker.com" ])
             {
                 dockerImage.push("${env.BUILD_NUMBER}")
                 dockerImage.push("latest")
            }
    }
  }
}    
                
             
        }
        
    }
