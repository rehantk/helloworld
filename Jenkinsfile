pipeline {
  agent any
  stages {
    stage('Code Analysis') {
      steps {
        withSonarQubeEnv('sonarqube')
          sh 'mvn sonar:sonar'
      }
    }
  }
}
