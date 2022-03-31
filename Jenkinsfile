pipeline {
  agent any
    stage('start') {
      steps {
        script {
        withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
          sh """
              docker login -u ${USERNAME} -p ${PASSWORD}
              docker build -t $DOCKER_REPO:latest .
              docker push $DOCKER_REPO:latest
          """
        }

      }
      }
    }
}
