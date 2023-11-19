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

        stage('Log Test') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automation file')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy application'
            input(message: 'Do you still want to deploy?', id: 'OK')
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = '/usr/local/bin'
  }
}