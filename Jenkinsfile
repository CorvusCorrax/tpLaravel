pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'composer install'
        sh 'cp .env.example .env'
        sh 'php artisan key:generate'
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