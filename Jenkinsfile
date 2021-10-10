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

    stage('artifact') {
      steps {
        archiveArtifacts(allowEmptyArchive: true, artifacts: 'rest-hateoas-complete-0.0.1-SNAPSHOT.jar')
      }
    }

  }
}