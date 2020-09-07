pipeline {
    agent any
    tools {
            maven 'apache-maven-3.5.0'

        }

    stages {
        stage ('Compile Stage') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage ('Testing Stage') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Sonarqube') {
            environment {
                scannerHome = tool 'sonar-scanner'
            }
            steps {
                withSonarQubeEnv('sonarqube') {
                    bat "${scannerHome}C:\Sonarqube\sonar-scanner-4.1.0.1829-windows"
                }
                timeout(time: 10, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
    }
}






