pipeline {
    agent any
    stages {
        stage('Build') { 
             steps {
                sh 'mvn clean package'
        }
        }
        stage('SonarQube') {
            steps {
                withSonarQubeEnv('sonar-way')
                { sh 'mvn sonar:sonar' }
            }
        }
        
        }
        
    }
