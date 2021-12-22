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
                SCANNER_HOME = tool 'SonarQubeScanner';
                PROJECT_NAME = "ISFinal"
            }

            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh '''$SCANNER_HOME/bin/sonar-scanner \
                            -Dsonar.projectKey=$PROJECT_NAME \
                            -Dsonar.sources=src/ \
                            -Dsonar.host.url=http://localhost:9000 \
                            -sonar.exclusions=node_modules/*, .git/*, .gitignore, public/*, __mocks__/*, src/components/__tests__/*, src/styles/* \
                            -Dsonar.login=9ffe0aa5b47596cd83f87c38835fe25a23c833ba''' 
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