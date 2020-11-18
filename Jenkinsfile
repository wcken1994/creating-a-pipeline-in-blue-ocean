pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh 'chmod +x ./jenkins/scripts/test.sh'
        sh 'ls -lhart'
        sh 'ls -lhart jenkins/scripts/'
        sh './jenkins/scripts/test.sh'
      }
    }

  }
}