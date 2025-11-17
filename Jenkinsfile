pipeline {
    agent any

    // Build parameters
    parameters {
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Application Version')
        booleanParam(name: 'EXECUTE_TESTS', defaultValue: true, description: 'Run Test Stage?')
        string(name: 'ENVIRONMENT', defaultValue: 'dev', description: 'Target Environment')
    }

    stages {

        stage('Build') {
            steps {
                echo "Building Version: ${params.VERSION}"
                echo "Target Environment: ${params.ENVIRONMENT}"
                echo "Build stage completed."
            }
        }

        stage('Test') {
            when {
                expression { params.EXECUTE_TESTS == true }
            }
            steps {
                echo "Tests Executing..."
                echo "Test stage completed."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying Version: ${params.VERSION} to ${params.ENVIRONMENT}"
            }
        }
    }

    post {
        always {
            echo "Pipeline finished."
        }
    }
}
