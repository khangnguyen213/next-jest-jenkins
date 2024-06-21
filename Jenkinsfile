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
        sh 'npm run test'
      }
    }

  }
}