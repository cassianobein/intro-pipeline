pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello ${MY_NAME}! '
        sh ' sh java --version'
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
  }
}