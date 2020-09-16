pipeline {
    environment {
registry = "nainikapanguluri/java_app1"
registryCredential = 'docker-hub'
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
              docker login -u nainikapanguluri -p NPnp1126$$$
            /* docker.withRegistry( 'https://registry.hub.docker.com', 'docker-hub' ) {*/
                 dockerImage.push("${env.BUILD_NUMBER}")
                 dockerImage.push("latest")
      
    }
  }
}    
                
             
        }
        
    }
