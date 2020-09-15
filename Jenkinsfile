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
           agent any
             steps {
                withSonarQubeEnv('sonar-way') { 
                sh 'mvn sonar:sonar'
                }
        }
        }
        
        }
        
    }
