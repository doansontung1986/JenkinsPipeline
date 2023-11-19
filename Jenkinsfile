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
            echo 'Testing application'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy application'
      }
    }

  }
}