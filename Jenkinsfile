pipeline {
  agent any
  stages {
    stage('activity2') {
      steps {
        sh 'git clone https://github.com/K-K-J/cicd-pipeline'
        sh '~/scripts/build.sh'
      }
    }

    stage('activity3') {
      steps {
        sh '~/scripts/test.sh'
      }
    }

  }
  environment {
    registry = 'https://github.com/K-chris703/cicd_jenkins'
  }
}