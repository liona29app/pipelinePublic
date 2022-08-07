pipeline {
  agent {
    node {
      label 'jenkins-slave'
    }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', 
      description: 'Who should I say hi to?')
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
//   environment {
//     Name = 'Ari'
//     TEST_USER = credentials('test-user')
//   }
}
