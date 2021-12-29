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

        stage('SonarQube Analysis') {

            environment{
                def SCANNER = tool name: 'SonarQubeScanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation';
            }

            steps {
                withSonarQubeEnv(installationName: 'sq1' ){
                    sh "${SCANNER}/bin/sonar-scanner"
                }
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
        
        stage('Git Checkout') {
            steps {
                sh 'git status'
                sh 'git add .'
            }
        }
    }
}