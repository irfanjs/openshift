pipeline {
agent any
stages {
  stage('Source Checkout') {
    steps {
    git url: "https://github.com/irfanjs/openshift.git"
    } 
  }
  
 
   stage('Build and Execute unit test cases') {
     steps {
     sh "sleep 1"
  /*  stash name:"jar", includes:"/var/lib/jenkins/jobs/coe-mern-project/jobs/coe-mern-project-petclinic-pipeline/workspace/target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar" */
      stash includes: "target/*.jar", name:"jar"
     }
    }
  
    stage('Execute Code quality') {
     steps {
       sh "sleep 1"
     
     } 
  }
    
  stage('publish test cases result') {
    steps {
       sh "sleep 1"
    }
  }
  
  stage('Record Jacoco coverage report') {
    steps {
       sh "sleep 1"
    }
  }
  
     
  /* stage('Execute Unit test(s)') {
     sh " cd /var/lib/jenkins/jobs/coe-mern-project/jobs/coe-mern-project-petclinic-pipeline/workspace"
     sh "/var/lib/jenkins/apache-maven-3.5.4/bin/mvn test -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=300"
      stash name:"jar", includes:"target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
    } */

/*  stage('Build and Deploy Image (frontend service) to Dev environment') {
    unstash name:"jar"
   sh "oc start-build testapp --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow --loglevel 10"
    sh "sleep 90"
   openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'
   openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'
  } */
  
  stage('Build and Deploy Services to Dev environment') {
      parallel {
      stage('frontend micro-service') {
      steps {
       sh "sleep 1"
      
     /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
     /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
     }
    }
    
     stage('admin micro-service') {
          steps {
              sh "sleep 1"
       /*  sh "oc start-build testapp --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow --loglevel 10" 
          sh "sleep 90" */
         /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
         /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
         }
    }
    
     stage('config micro-service') {
              steps {
                  sh "sleep 1"
             /*sh "oc start-build testapp --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow --loglevel 10"
              sh "sleep 90" */
             /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
             /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
             }
    }
    
  }       
  
  }
  
  stage('Execute smoke tests'){
    steps {
      sh 'curl -I http://testapp-jenkins.apps.na39.openshift.opentlc.com/'
  }
  }
  
  stage('Promote to QA environment') {
    steps {
      input 'Proceed to QA environment ?'
    }
  }
  
  stage('Build and Deploy Services to QA environment') {
      parallel {
      stage('frontend micro-service') {
      steps {
         sh "sleep 1"
      
     /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
     /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
     }
    }
    
     stage('admin micro-service') {
          steps {
              sh "sleep 1"
       /*  sh "oc start-build testapp --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow --loglevel 10" 
          sh "sleep 90" */
         /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
         /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
         }
    }
    
     stage('config micro-service') {
              steps {
                  sh "sleep 1"
             /*sh "oc start-build testapp --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow --loglevel 10"
              sh "sleep 90" */
             /*openshiftBuild apiURL: 'https://master.na39.openshift.opentlc.com', authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', buildName: 'target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar', bldCfg: 'mypet', checkForTriggeredDeployments: 'false', commitID: '', namespace: 'coe-mern-project', showBuildLogs: 'false', verbose: 'false', waitTime: '', waitUnit: 'sec'*/
             /*openshiftExec apiURL: 'https://master.na39.openshift.opentlc.com', arguments: [[value: 'petclinic-pipeline --from-file=target/spring-petclinic-openshift-2.0.0.BUILD-SNAPSHOT.jar --follow']], authToken: 'IdXwlyWZphf_A00Z9X02qMv57gyictVDMoBdA1PobQo', command: 'oc start-build', container: '', namespace: 'coe-mern-project', pod: 'jenkins-5-h7p9s', verbose: 'true', waitTime: '', waitUnit: 'sec'*/
             }
    }
    
  }       
  
  }

  
  
  stage("Functional Testing"){
    steps {
    sh "sleep 1"    
    }
   }

stage("Performance Testing"){    
  steps {
    sh "sleep 1"    
  }   
} 
}
}
