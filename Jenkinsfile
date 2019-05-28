pipeline {
  agent {
    docker {
      image 'node:latest'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello Build"'
      }
    }
    stage('Pull from Private Repository') {
      steps {
        git(url: 'https://github.com/48hands/udemy-akka-stream.git', credentialsId: 'MyGitHubAccount', branch: 'master', changelog: true)
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deployment starting..."'
      }
    }
  }
}