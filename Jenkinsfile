pipeline {
  agent {
    label 'jenkins-slave'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo "Hello ${params.Name}!"
        sh 'java -version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }

    stage('Get Kernel') {
      steps {
        script {
          try {
            KERNEL_VERSION = sh (script: "uname -r", returnStdout: true)
          } catch(err) {
            echo "CAUGHT ERROR: ${err}"
            throw err
          }
        }

      }
    }

    stage('Say Kernel') {
      steps {
        echo "${KERNEL_VERSION}"
      }
    }

    stage('Testing') {
      failFast true
      parallel {
        stage('Java 8') {
          agent {
            label 'jenkins-slave'
          }
          steps {
            sh 'java -version'
            sleep(time: 10, unit: 'SECONDS')
          }
        }

        stage('Java 9') {
          agent {
            label 'jenkins-jenkins-agent'
          }
          steps {
            sh 'java -version'
            sleep(time: 20, unit: 'SECONDS')
          }
        }

      }
    }
      stage('Checkpoint') {
         agent none
         steps {
            checkpoint 'Checkpoint'
         }
      }
      stage('Deploy') {
         agent none
         steps {
            echo 'Deploying....'
         }
      }
  }
  environment {
    MY_NAME = 'ari'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'
    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
