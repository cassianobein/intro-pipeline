pipeline {
  agent any
  stages {
    stage('Deploy') {
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
      }
    }
    stage('Deploy 2') {
      input {
        message 'Which Version?'
        id 'Deploy'
        parameters {
          choice(name: 'APP_VERSION', choices: '''v1.1
v1.2
v1.3''', description: 'What to deploy?')
        }
      }
      steps {
        echo "Deploying ${APP_VERSION}."
      }
    }
    stage('Say Hello') {
      steps {
        echo "Hello ${MY_NAME}!"
        echo "Hello ${params.Name}!"
        sh 'java -version'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}