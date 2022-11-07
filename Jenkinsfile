
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/astewart222/specialtopics-ci-lab'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
    withMaven (maven: 'maven3'){
        sh "mvn install"
    }
  }
  // you should add a test report here
  node {
     try {
        stage('Test') {
            eco "I'm testing!"
        }
     } finally {
        junit '**/target/test-reports/*.xml'
        }
  }
}
