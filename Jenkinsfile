pipeline {
    agent none
    stages {
        stage('Build') { 
            agent any
             steps {
                sh 'mvn clean package'
        }
        }
       stage('SonarQube analysis') { 
           agent { 
                label 'worker-linux'
            }
             steps {
                withSonarQubeEnv('sonar-way') { 
                sh 'mvn sonar:sonar'
                }
        }
        }
        
        }
        
    }
