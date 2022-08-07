pipeline {
  agent {
    node {
      label 'jenkins-slave'
    }

  }
  stages {
    stage('print') {
      steps {
        echo 'hello ari'
        sh 'java --version'
      }
    }

  }
}