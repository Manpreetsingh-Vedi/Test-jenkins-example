pipeline {
    agent any
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    Bat 'mvn install | mvn compile'
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
