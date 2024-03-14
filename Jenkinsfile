pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build App'
            }
        }

        stage('Test') {
            steps {
                echo 'Test App'
            }
            post {
                success {
                    emailext body: 'Testing has passed successfully', subject: 'Testing Status', to: 'khushi1317@gmail.com'
                }
            }
        }

        stage('Security') {
            steps {
                echo 'Perform Security Checks'
            }
            post {
                success {
                    emailext body: 'Security checks have passed successfully', subject: 'Security Status', to: 'khushi1317@gmail.com'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy App'
            }
        }
    }

    post {
        always {
            emailext body: 'Summary', subject: 'Pipeline Status', to: 'khushi1317@gmail.com'
        }
    }
}
