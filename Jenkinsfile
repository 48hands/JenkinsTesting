pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello Build"'
      }
    }
    stage('GitPull') {
      parallel {
        stage('GitPull') {
          steps {
            git(url: 'https://github.com/48hands/ruby-study.git', branch: 'master', changelog: true, credentialsId: 'TestUserId')
            sh 'ls -la'
          }
        }
        stage('GitPull2') {
          steps {
            git(url: 'https://github.com/48hands/scala-advanced-learning.git', credentialsId: 'MyGitHubAccount', branch: 'master')
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deployment starting..."'
      }
    }
  }
}