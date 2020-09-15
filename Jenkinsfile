pipeline {
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
            steps {
                sh '''
                docker login -u nainikapanguluri -p NPnp1126$$$
                  docker build -t nainikapanguluri/java_app .
                  docker push nainikapanguluri/java_app
                  
                 '''
                    }
             }
        }
        
    }
