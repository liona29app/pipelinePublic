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
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }

  }
  environment {
    Name = 'Ari'
    TEST_USER = credentials('test-user')
  }
}
