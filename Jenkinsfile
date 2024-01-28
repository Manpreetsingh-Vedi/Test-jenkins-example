pipeline {
    agent any
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    Bat '"C:\Program Files\apache-maven-4.0.0-alpha-8\bin" clean compile'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    Bat 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    Bat 'mvn deploy'
                }
            }
