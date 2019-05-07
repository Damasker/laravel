pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh label: '', script: '''composer install
                                         php artisan key:generate
                                         php artisan migrate:refresh
                                         php artisan migrate --seed
                                         php artisan vendor:publish''' 
                ftpPublisher alwaysPublishFromMaster: false, continueOnError: false, failOnError: false, publishers: [[configName: 'example.com', transfers: [[asciiMode: false, cleanRemote: false, excludes: '', flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.*']], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false]]
            }
        }
    }
}
