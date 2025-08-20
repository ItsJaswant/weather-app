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
                sh 'cd <path_to_your_project>'
                sh './build.sh'  // Assuming you have a build script named build.sh
            }
        }

        stage('Run Tests') {
            steps {
                sh 'cd <path_to_your_project>'
                sh './test.sh'  // Assuming you have a test script named test.sh
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
