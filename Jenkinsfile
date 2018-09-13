node {
  stage('Build') {
    git url: "https://github.com/siamaksade/cart-service.git"
    sh "mvn package"
    stash name:"jar", includes:"target/cart.jar"
  }
 } 