pipeline {
  agent {
      label 'jenkins-slave'
    }
  environment {
    Name = 'Ari'
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

}
