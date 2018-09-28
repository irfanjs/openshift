pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat(script: 'mvn clean package', returnStdout: true)
      }
    }
    stage('execute code quality') {
      steps {
        bat(script: 'mvn sonar:sonar -Dsonar.host.url=http://sonarqube-jenkins.apps.na39.openshift.opentlc.com', returnStdout: true)
      }
    }
    stage('unit test result') {
      steps {
        junit(testResults: '**/target/surefire-reports/TEST*.xml', allowEmptyResults: true)
      }
    }
    stage('publish code coverage') {
      steps {
        jacoco()
      }
    }
    stage('Upload artifact (Nexus)') {
      steps {
        bat(script: 'REM mvn deploy', returnStdout: true)
      }
    }
  }
}