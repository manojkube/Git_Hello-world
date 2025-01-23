pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TESt-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'maven39'
  }
}
