pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: '', url: 'https://github.com/ItsJaswant/weather-app/'
            }
        }

        stage('Build Project') {
            steps {
                echo 'ℹ️ No build required. Static files only.'
            }
        }

        stage('Archive Website') {
            steps {
                archiveArtifacts artifacts: '**/*', fingerprint: true
            }
        }
    }


    post {
        always {
            archiveArtifacts artifacts: '**/*.log' // Archive logs from all stages
            // mail to: 'you@example.com', subject: 'Build Logs', body: 'Build finished'
        }
        success {
            echo '✅ Build and tests completed successfully!'
        }
        failure {
            echo '❌ Build or tests failed!'
        }
    }
}
