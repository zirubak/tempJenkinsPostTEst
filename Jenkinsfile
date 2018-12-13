pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh 'make check'
      }
    }
    stage('error') {
      steps {
        emailext(subject: 'packager-maintenance', body: 'Check the build result.', to: '\'18582105171@tmomail.net\'')
      }
    }
  }
  post {
    always {
      junit '**/target/*.xml'

    }

    failure {
      echo 'FAIL'

    }

  }
}