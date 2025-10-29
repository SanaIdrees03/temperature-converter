pipeline {
    agent any

    environment {
        APP_VERSION = "1.1.0"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }

    post {
        success {
            echo "Build completed successfully! ✅"
        }
        failure {
            echo "Build failed ❌"
        }
    }
}
