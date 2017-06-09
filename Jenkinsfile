pipeline {
  agent any
  triggers {
    pollSCM('* * * * *')
  }
  stages {
    stage('build') {
      steps {
        sh 'composer install'
      }
    }
        stage('Lauch test'){
            steps {
                sh './tpLaravel/vendor/bin/phpunit  ./tpLaravel/tests/Unit/ExampleTest.php'
            }
        }

        stage('Deploy') {
            steps {
                sh "echo bonjour"
                sh "cd tpLaravel && rocketeer deploy"
            }
        }
  }
}
