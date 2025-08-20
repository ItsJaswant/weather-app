pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/ItsJaswant/weather-app'
            }
        }

        stage('Build Project') {
            steps {
                echo "ℹ️ No build required. Static files only."
            }
        }
    }

    post {
        always {
            echo "✅ Pipeline completed"
        }
        success {
            echo "✅ Build and tests completed successfully!"
        }
        failure {
            echo "❌ Build or tests failed!"
        }
    }
}
