pipeline {
  agent any
  stages {
    stage('first') {
      steps {
        sh '''#!/bin/bash

echo "##JH## `cat BUILD_VERSION.txt`"
echo "##JH## `pwd`"
echo "##JH## $WORKSPACE"

'''
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