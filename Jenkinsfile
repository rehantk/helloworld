
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
        stage ('Bulding Docker image){
            steps {
                sh 'docker build -t mydeploytomcat .'
                }
        }
        stage ('Deploy in Tomcat container'){
            steps {
                sh 'docker run -p 8080:8080 -d mydeploytomcat'
                }
        }
    }
}
