// http://vgaidarji.me/blog/2018/07/30/working-with-jenkinsfile-in-intellij-idea/
pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Build'){
      steps{
        sh 'node --version'
        sh 'pwd'
      }
    }
  }
}
