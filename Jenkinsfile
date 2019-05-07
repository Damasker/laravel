pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh label: '', script: '''composer install
                                         php artisan key:generate
                                         php artisan db:refresh
                                         php artisan migrate --seed
                                         php artisan vendor:publish''' 
            }
        }
    }
}
