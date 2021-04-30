pipeline {
  agent any
  stages {
    stage('Stage 1') {
      steps {
        sh 'mvn sonar:sonar -D sonar.login=sonar -D sonar.password=sonar'
      }
    }
  }
}
