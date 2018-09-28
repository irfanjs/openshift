pipeline {
  agent any
  stages {
    stage('execute code quality') {
      steps {
        sh ' sh "/var/lib/jenkins/apache-maven-3.5.4/bin/mvn sonar:sonar -Dsonar.host.url=http://sonarqube-jenkins.apps.na39.openshift.opentlc.com"'
      }
    }
  }
}