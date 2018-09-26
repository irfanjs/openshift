pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat(returnStatus: true, returnStdout: true, script: 'a.bat')
      }
    }
  }
}