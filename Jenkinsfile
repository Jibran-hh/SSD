flag = true

pipeline {
    agent any

    // Tools available for all stages
    tools {
        maven 'Maven'    // <-- This must match EXACTLY the name in Jenkins → Tools
    }

    // Environment variables
    environment {
        VERSION = "1.0.5"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Project with version: ${VERSION}"

                // Verify maven installation
                sh "mvn --version"     // Windows: bat 'mvn --version'
            }
        }

        stage('Test') {
            when {
                expression {
                    flag == true
                }
            }
            steps {
                echo "Testing Project (Version: ${VERSION})"
                script {
                    flag = false
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Project Version: ${VERSION}"
            }
        }
    }

    post {
        always {
            echo 'Post build condition running'
        }
        failure {
            echo 'Post Action if Build Failed'
        }
    }
}
