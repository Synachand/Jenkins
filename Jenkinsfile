pipeline {
  agent none
  stages {
    stage('Back-end') {
      agent {
        docker { image 'maven:latest' }
      }
      steps {
        sh 'sudo chown -R docker:ubuntu /var/run/docker.sock'
        sh 'sudo chmod 666 /var/run/docker.sock'
        sh 'mvn -version'
      }
    }
    stage('Front-end') {
      agent {
        docker { image 'node:16-alpine' }
      }
      steps {
        sh 'node -version'
      }
    }
  }
}
