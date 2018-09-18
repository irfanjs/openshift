node {
  stage('Source Checkout') {
    git url: "https://github.com/irfanjs/openshift.git"
  }
  
   stage('Build') {
      git url: "https://github.com/irfanjs/openshift.git"
      sh "pwd"
      sh "/var/lib/jenkins/apache-maven-3.5.4/bin/mvn clean package -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=300"
  /*  stash name:"jar", includes:"/var/lib/jenkins/jobs/coe-mern-project/jobs/coe-mern-project-petclinic-pipeline/workspace/target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar" */
      stash includes: "target/*.jar", name:"jar"
    }
    
  /* stage('Execute Unit test(s)') {
     sh " cd /var/lib/jenkins/jobs/coe-mern-project/jobs/coe-mern-project-petclinic-pipeline/workspace"
     sh "/var/lib/jenkins/apache-maven-3.5.4/bin/mvn test -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=300"
      stash name:"jar", includes:"target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
    } */

  stage('Build Image') {
    unstash name:"jar"
    sh "oc start-build petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow"
  }
 } 