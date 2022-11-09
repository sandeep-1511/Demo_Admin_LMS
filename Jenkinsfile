pipeline {
    agent any

    stages {
        stage('Slack Notification') {
            steps {
                script {
                    slackSend channel: 'jenkins-pipeline-updates', message: 'slackSend "started ${env.JOB_NAME} ${env.BUILD_NUMBER} (<http://54.183.83.72:8080/job/admin-lms/${env.BUILD_NUMBER}/console|Open>)"', teamDomain: 'jenkinspipeli-qm51342', tokenCredentialId: 'slackusernew'
                }
            }
        }
        stage('Docker BUILD image & Push to S3 bucket') {
            steps {
                sh 'docker build -t admin .'
            }
        }
    }
}
