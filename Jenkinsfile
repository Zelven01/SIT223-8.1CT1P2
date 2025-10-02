pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Zelven01/SIT223-8.1CT1P2.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Allows pipeline to continue despite test failures
                sh 'npm test || true'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                // Ensure coverage report exists
                sh 'npm run coverage || true'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                // Show known CVEs in the output
                sh 'npm audit || true'
            }
        }
    }
}
