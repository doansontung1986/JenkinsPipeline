pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building application'
          }
        }

        stage('Test') {
          steps {
            echo "Testing application ${ChromeDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy application'
        input(message: 'Do you still want to deploy?', id: 'OK')
      }
    }

  }
  environment {
    ChromeDriverPath = '/usr/local/bin'
  }
}