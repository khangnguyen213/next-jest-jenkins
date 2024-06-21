pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/khangnguyen213/next-jest-jenkins', branch: 'main')
      }
    }

    stage('build') {
      steps {
        echo 'Building the app'
        sh 'npm ci'
        sh 'npm run build'
      }
    }

    stage('test') {
      steps {
        echo 'Testing the app'
        sh 'npm run test'
      }
    }

    stage('docker') {
      steps {
        withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
          sh 'docker build -t kannguyen1010/next-jest-jenkins .'
          sh 'docker push kannguyen1010/next-jest-jenkins'
}
      }
    }

  }
}