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
                  docker build -t nainikapanguluri/java_app .
                  docker push nainikapanguluri/java_app
                 '''
                    }
             }
        }
        
    }
