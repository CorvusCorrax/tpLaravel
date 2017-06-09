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
        sh './vendor/bin/phpunit  ./tests/Unit/ExampleTest.php'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo bonjour'
        sh 'cd tpLaravel && rocketeer deploy'
      }
    }
  }
  triggers {
    pollSCM('* * * * *')
  }
}