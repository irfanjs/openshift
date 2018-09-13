node {
  stage('Build') {
    git url: "https://github.com/irfanjs/openshift.git"
    sh "mvn clean package"
    stash name:"jar", includes:"target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
  }
 } 