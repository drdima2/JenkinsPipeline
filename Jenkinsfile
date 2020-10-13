// http://vgaidarji.me/blog/2018/07/30/working-with-jenkinsfile-in-intellij-idea/
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

        stage('Test Log') {
          environment {
            LocalVariable2 = 'HelloLocal'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This ChromeDriverPath ${ChromeDriverPath} and localVariableValue ${LocalVariable2}")
          }
        }

      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      parallel {



        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deployment ?', id: 'OK')
            echo 'Deploying the app'
          }
        }

        stage('Atrifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path\\1'
  }
}
