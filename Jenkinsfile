pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main',
                    url: 'https://github.com/nravinuthala/pipelines-java-1.git'
            }
        }
        
        stage('Compile') {
            steps {
                sh "mvn compile"
            }

        }
        stage ("Test") {
            steps {
                sh "mvn test"
            }
        }
        stage('Package') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

            }
        }
    }
}
