pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('mominhuzaifa', "g'S2FQW#8vz.5,h")
  }
  stages {
    stage('Build - building docker image') {
      steps {
        sh 'docker build -t mominhuzaifa/jenkins-docker-image .'
      }
    }
    stage('Login - logging at dockerhub') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push - pushing at dockerhub') {
      steps {
        sh 'docker push mominhuzaifa/jenkins-docker-hub'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}