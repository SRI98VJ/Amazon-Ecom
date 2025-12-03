pipeline {
  agent any
  environment {
    GIT_BRANCH = 'master'
    // IMPORTANT: Use YOUR forked repo URL here
    GIT_URL = 'https://github.com/SRI98VJ/Amazon-Ecom.git'
  }
  stages {
    stage('clone project') {
      steps {
        // Note: Jenkinsfile uses double quotes for Groovy variable interpolation
        git branch: "${GIT_BRANCH}", url: "${GIT_URL}" 
      }
    }
    stage('clean') {
      steps {
        sh 'mvn clean'
      }
    }
    stage('compile') {
      steps {
        sh 'mvn compile' // Class script examples use 'mvn compile' [cite: 10, 26]
      }
    }
    stage('test') {
      steps {
        sh 'mvn test'
      }
    }
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
  }
}
