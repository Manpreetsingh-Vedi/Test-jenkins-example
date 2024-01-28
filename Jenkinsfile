pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(MVN_HOME : '4.0.0-alpha-8') {
                    mvn clean compile
                }
            }
        }

    }
}
