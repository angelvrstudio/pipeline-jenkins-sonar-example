pipeline {
    agent any
tools {
        maven 'Maven 3.5.0'
        jdk 'jdk8'
    }
    stages {
        stage ('Compile Stage') {

            steps {
            with Maven
                {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
            with Maven
                {
                    sh 'mvn test'
                }
            }
        }
        stage ('Deployment Stage') {
            steps {
            with Maven
                 {
                    sh 'mvn deploy'
                }
            }
        }
    }
}