pipeline {
  agent {
    docker {
      image 'azul/zulu-openjdk:8u265'
    }

  }
  stages {
    stage('test') {
      steps {
        sh '''cd complete
mvn test'''
      }
    }

  }
}