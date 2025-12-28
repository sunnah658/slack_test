pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'exit 1'
            }
        }
    }

    post {
        success {
            slackSend(channel: 'C0A5QGT2GRK', message: "✅ Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
        failure {
            slackSend(channel: 'C0A5QGT2GRK', message: "❌ Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
    }
}
