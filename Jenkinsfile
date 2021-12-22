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

                try {
                    sh 'git commit -m "Jenkinsfile"'
                }
                catch {
                    sh 'echo rama actualizada'
                }
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