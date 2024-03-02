pipeline {
  agent any
  stages {
    stage('activity1 - github clone') {
      steps {
        sh ' echo \'$DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin\' &&   echo\'Login complete\''
        sh 'git clone https://github.com/K-K-J/cicd-pipeline ~/cicd_task/final'
        sh ''' cd ~/cicd_task/final
'''
        sh 'pwd'
        sh 'ls'
      }
    }

    stage('activity2 - build') {
      steps {
        sh '''pwd 
cd ~/cicd_task/final/scripts/ && ls -la && chmod +x build.sh && ./build.sh'''
        sh '''sudo ~/cicd_task/final/scripts/build.sh

'''
      }
    }

    stage('activity3 - test') {
      steps {
        sh 'cd ~/cicd_task/final/scripts/ && chmod +x test.sh && ./test.sh'
      }
    }

    stage('activity4 - docker build') {
      steps {
        sh 'cd ~/cicd_task/final/ && ls'
        sh 'docker build -t activity4-5 .'
      }
    }

    stage('activity5 - docker push') {
      steps {
        sh 'cd ~/cicd_task/final/'
        sh 'sudo docker image tag task4 chris703/task4-5:latest && sudo docker image push chris703/task4-5:latest'
      }
    }

  }
  environment {
    registry = 'chris703/cicd_jenkins'
    DOCKERHUB_CREDENTIALS = 'credentials(\'dockerhub\')'
  }
}