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
        sh '''chmod +x ./jenkins/scripts/test.sh
ls -lhart
ls -lhart jenkins/scripts/
./jenkins/scripts/test.sh'''
      }
    }

  }
}