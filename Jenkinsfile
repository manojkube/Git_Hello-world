pipeline {
  agent any
  tools {
    maven 'maven39'
  }
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
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }
    stage('Deploy') {
      steps {
        sh """ java -jar target/hello-demo-*.jar > dev/null &  """
      }
    }
    stage('Unit Test') {
      steps {
        sh 'sleep 10'
        sh 'curl -s http://localhost:6767/hello'
     }
    }
 }
}
