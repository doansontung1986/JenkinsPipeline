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
            echo "Testing application"
            echo "Get the driver path at ${ChromeDriverPath}"
          }
        }

        stage('Test Log') {
          environment {
              LocalVariable = 'Hello Local'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is an automation file: ${LocalVariable}")
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
