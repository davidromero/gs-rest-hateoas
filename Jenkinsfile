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
mvn clean test site'''
      }
    }

    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh '''cd complete
mvn package'''
          }
        }

        stage('publish results') {
          steps {
            junit '**/surefire-report.html'
          }
        }

      }
    }

    stage('artifact') {
      steps {
        archiveArtifacts(allowEmptyArchive: true, artifacts: 'complete/target/rest-hateoas-complete-0.0.1-SNAPSHOT.jar')
      }
    }

  }
}