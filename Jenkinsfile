pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage ('Testing'){
            steps {
                sh ' mvn test'
            }
        }
        stage ('Scanning'){
            steps {
                withCredentials([string(credentialsId: 'sonarcube', variable:'Token')]){
                    sh ' mvn sonar:sonar -D sonar.login=${Token)'
                }
            }
        }
    }
}
