pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'composer install'
      }
    }
    stage('Lauch test') {
      steps {
        sh './vendor/bin/phpunit'
      }
    }
    stage('Deploy') {
      steps {
        sh 'rocketeer deploy'
      }
    }
  }
  triggers {
    pollSCM('* * * * *')
  }
}