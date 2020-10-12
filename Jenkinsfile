pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the app'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing app'
            echo "Get the DriverPath ${ChromeDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy ?', id: 'OK')
        echo 'Deploying the app'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path\\1'
  }
}