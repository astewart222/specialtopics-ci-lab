
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
    try {
        stage('Test') {
            sh "./maven3"
        }
       } finally {
        archiveArtifacts archiveArtifacts: 'build/libs/**/*.jar', fingerprint: true
        junit 'build/reports/**/*.xml'
       }
}
