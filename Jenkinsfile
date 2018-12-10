pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo start maven '
      }
    }
    stage('SonarQube test') {
      environment {
        sonarqube_URL = 'http://34.243.140.71:9000'
      }
      steps {
        sh 'echo mvn sonar:sonar -url ${sonarQube_URL}'
      }
    }
    stage('Build validation') {
      steps {
        input(message: 'Validate build', ok: 'Yes')
      }
    }
    stage('Packaging') {
      steps {
        sh 'echo push to JFROG'
      }
    }
  }
}