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
                def SCANNER = tool 'sonarqube';
            }
            
            withSonarQubeEnv('sonarqube'){
                sh "${SCANNER}/bin/sonar-scanner \
                    -Dsonar.projectKey=ISFinal \
                    -Dsonar.sources=src/ \
                    -Dsonar.host.url=http://localhost:9000 \
                    -sonar.exclusions=node_modules/, .git/, .gitignore, public/, _mocks/*, src/components/, src/components/_tests_/, src/styles/ \
                    -Dsonar.login=9ffe0aa5b47596cd83f87c38835fe25a23c833ba"
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