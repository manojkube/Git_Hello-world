pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven39"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                // git branch: 'main', url: 'https://github.com/manojkube/Git_Hello-world.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
    }
}
