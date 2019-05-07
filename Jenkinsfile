pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'composer install' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
    }
}
