pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      environment {
        CI = 'true'
      }
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'sh \'./jenkins/scripts/test.sh\''
      }
    }

    stage('end') {
      steps {
        sh 'sh \'./jenkins/scripts/kill.sh\''
      }
    }

  }
}