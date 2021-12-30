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

        stage('JMETER - Build') {
            steps {
                sh """
                   date
                   echo Starting the Performance Test 
                   """
                
                sh """ 
                   cd /media/luismoroco/D/Clases/3ERO/IS/apache-jmeter-5.4.1/bin/
                   sh jmeter.sh -Jjmeter.save.saveservice.output_format=xml -n -t /media/luismoroco/D/Portafolio/ProjectFinal/JmeterJenkinsTest.jmx -l /home/luismoroco/Escritorio/TestJenkinsJmeter.jtl
                   """
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