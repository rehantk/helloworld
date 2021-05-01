pipeline {
  agent any
  stages {
    stage('Code Analysis') {
        def mvnHome = tool name: 'maven3', type: 'maven'
        withSonarQubeEnv('sonarcube') {
          sh "${mvnHome}/bin/mvn sonar:sonar"
      }
    }
  }
}
