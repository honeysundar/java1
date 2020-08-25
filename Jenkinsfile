pipeline {
    agent { label 'worker' }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
    
}

            
