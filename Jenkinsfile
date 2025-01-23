pipeline {
  agent any
  tools {
    maven 'maven39'
  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

  }
}
