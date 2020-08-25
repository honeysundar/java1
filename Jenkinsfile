pipeline {
    agent { label 'awsworker' }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
    
}

            
