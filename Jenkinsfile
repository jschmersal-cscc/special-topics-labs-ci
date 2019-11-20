
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/pparasuram/special-topics-labs-ci'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
    withMaven (maven: 'maven3') {
       sh "mvn install"
    }
    echo "hello prakash clueless Jenkins"
  }
  // you should add a test report here
    try {
        stage('Test') {
            sh 'mvn test'
        }
    } finally {
        junit 'target/surefire-reports/**/*.xml'
    }
}
