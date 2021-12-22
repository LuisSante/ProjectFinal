pipeline {
    agent any
    environment {
            CI = 'true'
        }
    stages {
        stage('Git Checkout') {
            steps {
                sh 'git status',
                sh 'git add .',
                sh 'git commit -m "Jenkinsfile"'
            }
        }
        stage('Install') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Test') {
            steps {
                sh 'yarn test'
            }
        }
    }
}