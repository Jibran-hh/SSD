flag = true

pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Project'
            }
        }

        stage('Test') {
            when {
                expression {
                    flag == true       // Run Test stage only if condition is true
                }
            }
            steps {
                echo 'Testing Project'
                script {
                    flag = false      // Example: update flag inside script block
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Project'
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
