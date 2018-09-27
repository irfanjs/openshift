pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat(script: 'mvn clean package', returnStdout: true)
      }
    }
  }
}