pipeline {
  agent any
  stages {
    stage('Code Analysis') {
      steps {
        sh 'mvn sonar:sonar -D sonar.login=sonar -D sonar.password=sonar'
      }
    }
    stage("Quality Gate") {
      steps {
        timeout(time: 1, unit: 'HOURS') {
          waitForQualityGate abortPipeline: true
      }
    }
  }
}
