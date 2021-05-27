
pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage ('Code compile'){
            steps {

                sh 'mvn clean package'
            }
        }
        stage ('Code Test'){
            steps {
                sh 'mvn test'
            }
        }
        stage ('Scanning'){
            steps {
                withCredentials([string(credentialsId: 'sonarcube', variable:'Token')]){
                    sh ' mvn sonar:sonar -D sonar.login=${Token}'
                }
            }
        }
        stage ('Deploy to localrepo'){
            steps {
                sh 'mvn install'
                }
        }
    }
}
