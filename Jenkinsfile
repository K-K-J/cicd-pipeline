pipeline {
  agent any
  stages {
    stage('activity2') {
      steps {
        sh 'git clone https://github.com/K-K-J/cicd-pipeline ~/cicd_task/final'
        sh ''' cd ~/cicd_task/final
'''
        sh 'ls'
      }
    }

  }
  environment {
    registry = 'chris703/cicd_jenkins'
  }
}