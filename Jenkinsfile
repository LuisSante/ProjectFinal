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

        stage('SonarQube Analysis') {
            
            environment{
                def SCANNER = tool 'sonarqube'
            }

            steps {
                withSonarQubeEnv('sonarqube'){
                    sh "${SCANNER}/bin/sonar-scanner" 
                }
            }

        }

        stage('Build') {
            steps {
                sh 'yarn build'
            }
        }
        
        stage('Git Checkout') {
            steps {
                sh 'git status'
                sh 'git add .'
            }
        }
    }
}