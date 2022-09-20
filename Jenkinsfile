pipeline {
  agent any
  stages {
    stage('prepare playwright') {
      steps {
        sh '''
          npm i -D @playwright/test
          npm install fs-extra
          npx playwright install
        '''
      }
    }
    stage('help') {
      steps {
        sh 'npx playwright test --help'
      }
    }
    stage('test') {
      steps {
        sh '''
          npx playwright test --list
          npx playwright test
        '''
      }
    }
  }
}