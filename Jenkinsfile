pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage ('Testing'){
            steps {
                sh 'mvn test sonar:sonar'
            }
        }
    }
}
