pipeline {
  agent {
    docker {
      image 'azul/zulu-openjdk-alpine:8u302-8.56.0.21-jre'
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