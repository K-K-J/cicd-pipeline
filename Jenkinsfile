pipeline {
  agent any
  stages {
    stage('activity2') {
      steps {
        sh '~/scripts/build.sh'
        sh 'git clone https://github.com/K-K-J/cicd-pipeline'
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