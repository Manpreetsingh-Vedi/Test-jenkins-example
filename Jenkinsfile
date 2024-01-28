pipeline {
    agent any
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    bat 'mvn clean install'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    bat 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    bat 'mvn deploy'
                }
            }
