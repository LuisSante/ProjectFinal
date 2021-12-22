pipeline {
    agent any
    environment {
            CI = 'true'
        }
    stages {
        stage('Git Checkout') {
            steps {
                sh 'git status'
                sh 'git add .'
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
        stage('Build') {
            steps {
                sh 'yarn build'
            }
        }
    }
}