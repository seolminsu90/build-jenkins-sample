pipeline {
  agent any
  stages {
    stage('source') {
      steps {
        git(url: 'https://github.com/seolminsu90/build-jenkins-sample.git', branch: 'master')
      }
    }

    stage('build') {
      steps {
        sh 'echo \'build project....\''
      }
    }

    stage('deploy') {
      environment {
        stage = 'dev'
      }
      parallel {
        stage('deploy to dev') {
          steps {
            sh 'echo \'deploy complete\''
          }
        }

        stage('deploy to live') {
          steps {
            sh 'echo \'deploy to live\''
          }
        }

      }
    }

  }
}