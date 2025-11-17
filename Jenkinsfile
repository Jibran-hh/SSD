pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

    }

    post {
        // The conditions here will execute after the build is done

        always {
            // This action will run regardless of build result
            echo 'Post build condition running'
        }

        failure {
            // This runs only if the build fails
            echo 'Post Action if Build Failed'
        }
    }
}
