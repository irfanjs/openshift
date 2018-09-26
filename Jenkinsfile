pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean package jacoco:prepare-agent jacoco:report'
      }
    }
  }
}