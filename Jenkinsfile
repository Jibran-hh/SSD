flag = true

pipeline {
    agent any

    // Environment variables available to all stages
    environment {
        VERSION = "1.0.5"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Project with version: ${VERSION}"
            }
        }

        stage('Test') {
            when {
                expression {
                    flag == true      // Run test stage only if flag is true
                }
            }
            steps {
                echo "Testing Project (Version: ${VERSION})"
                script {
                    flag = false     // Update the flag after running tests
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
