pipeline {
    agent {
        docker { image 'node:14' }
    }

    stages {
        stage('Checkout') {
            steps {
                // Pulls code from your GitHub repo
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
                sh 'npm test || true'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                sh 'npm run coverage || true'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                sh 'npm audit || true'
            }
        }
    }
}
