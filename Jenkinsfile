pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : '4.0.0-alpha-8') {
                    sh 'mvn clean compile'
                }
            }
        }

    }
}
