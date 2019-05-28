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
    stage('Pull from Public Repository') {
      steps {
        sh 'echo "Deployment starting..."'
        git(url: 'https://github.com/48hands/ruby-study.git', branch: 'master', changelog: true)
      }
    }
  }
}