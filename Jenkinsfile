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
        stage('Start') {
            steps{
                sh 'yarn start'
            }
        }
    }
}