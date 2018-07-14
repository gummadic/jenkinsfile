pipeline {
  agent any
  stages {
    stage('Example Build') {
      parallel {
        stage('Example Build') {
          agent {
            docker 'maven:3-alpine'
          }
          steps {
            echo 'Hello, Maven'
            sh 'mvn --version'
          }
        }
        stage('test') {
          steps {
            sh 'echo "hi"'
          }
        }
      }
    }
    stage('Example Test') {
      parallel {
        stage('Example Test') {
          agent {
            docker 'openjdk:8-jre'
          }
          steps {
            echo 'Hello, JDK'
            sh 'java -version'
          }
        }
        stage('') {
          steps {
            bat 'test'
          }
        }
      }
    }
  }
}