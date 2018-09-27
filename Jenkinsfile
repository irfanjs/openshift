pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat(script: 'a.bat', returnStatus: true, returnStdout: true)
      }
    }
  }
}