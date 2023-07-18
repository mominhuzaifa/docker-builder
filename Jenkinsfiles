pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        sh 'echo Docker Builder Pipeline in Jenkins'
      }
    }
  }

}
