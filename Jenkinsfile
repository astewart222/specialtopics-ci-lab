
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/astewart222/specialtopics-ci-lab'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
    withMaven (maven: 'maven3'){
        sh "mvn package"
    }
  }

 stage('Test'){
    junit '**/target/surefire-reports/*.xml'
 }

}
