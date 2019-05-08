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
               ftpPublisher masterNodeName:'', paramPublish:[parameterName:''], alwaysPublishFromMaster: false, continueOnError: false, failOnError: false, publishers: [[configName: '78.46.223.135', transfers: [[asciiMode: false, cleanRemote: false, excludes: '', flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/httpdocs', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '/storage/**/**']], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false]]
            }
        }
    }
}
