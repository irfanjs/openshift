pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat(script: 'mvn clean package', returnStdout: true)
      }
    }
    stage('unit test result') {
      steps {
        junit(allowEmptyResults: true, testResults: '**/target/surefire-reports/TEST*.xml')
      }
    }
    stage('publish code coverage') {
      steps {
        jacoco()
      }
    }
  }
}