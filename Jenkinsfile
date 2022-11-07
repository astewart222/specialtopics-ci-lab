
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
  // you should add a test report here
  node {
     try {
        stage('Test') {
            echo "I might pass this test!"
        }
     } finally {
        junit 'build/reports/**/*.xml'
        }
  }
}
