pipeline {
  agent {
    docker {
      image 'maven:3.6-jdk-8'
    }

  }
  stages {
    stage('test') {
      steps {
        sh '''cd complete
mvn test'''
      }
    }

    stage('build') {
      steps {
        sh '''cd complete
mvn package'''
      }
    }

  }
}