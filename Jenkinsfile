pipeline {
  agent {
    node {
      label 'jenkins-slave'
    }

  }
  stages {
    stage('print') {
      steps {
        echo "hello ${Name}"
        sh 'java --version'
      }
    }

  }
  environment {
    Name = 'Ari'
  }
}