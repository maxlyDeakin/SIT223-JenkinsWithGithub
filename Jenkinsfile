pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Example: sh 'scp -r target/ user@staging-server:/path/to/deploy/'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Hi",
                body: """Hello""",
                to: 'maxly746@gmail.com',
                attachLog: true
            )
        }
    }
}
