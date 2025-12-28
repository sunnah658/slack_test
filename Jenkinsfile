pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
                // Simulating build step
                sh 'echo Hello World'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                // Simulating test step
                //sh 'exit 1' // Change to 'exit 1' to test failure notification
            }
        }
    }

    post {
        success {
            slackSend(
                channel: 'C0A5QGT2GRK', 
                message: "✅ SUCCESS: Job '${JOB_NAME} [${BUILD_NUMBER}]' completed successfully!\n${BUILD_URL}",
                color: '#36a64f'
            )
        }
        failure {
            slackSend(
                channel: 'C0A5QGT2GRK', 
                message: "❌ FAILURE: Job '${JOB_NAME} [${BUILD_NUMBER}]' failed!\n${BUILD_URL}",
                color: '#ff0000'
            )
        }
    }
}
