pipeline {
    agent any
    environment {
            CI = 'true'
        }
    stages {
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
        stage('Start') {
            steps{
                sh 'yarn start'
            }
        }
    }
}