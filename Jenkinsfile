pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        post {
        always {
            emailext(
                subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                body: """Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}
                        Check console output at """,
                to: 'maxly746@gmail.com',
                attachLog: true
            )
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
        post {
        always {
            emailext(
                subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                body: """Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}
                        Check console output at """,
                to: 'maxly746@gmail.com',
                attachLog: true
            )
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
}
