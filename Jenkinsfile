
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/melanie-oneill/special-topics-labs-ci.git'
  }

  stage('Build') {
    // you should build this repo with a maven build step here
    echo "hello world"
    withMaven (maven: 'maven3') {
          sh "mvn package"
        }
  }
    try{
      stage('UnitTest') {
        withMaven (maven: 'maven3') {
          sh "mvn test"
        }
      }
    }finally{
      echo "hello test"
        junit 'target/surefire-reports/**/*.xml'
        }
  }
