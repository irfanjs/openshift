node {
  stage('Build') {
    git url: "https://github.com/irfanjs/openshift.git"
    sh "/var/lib/jenkins/apache-maven-3.5.4/bin/mvn clean package -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=300"
    stash name:"jar", includes:"target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
  }
 } 