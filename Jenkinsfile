pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project'
            }
        }
        stage('Tests') {
            steps {
                echo 'Run unit and integration tests...'
            }
            post {
                always {
                    emailext(
                        subject: "Test build ${currentBuild.currentResult}",
                        body: "Test build ${currentBuild.currentResult}.",
                        to: 'maxly746@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyze code...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Perform security scan...'
            }
            post {
                always {
                    emailext(
                        subject: "Security build ${currentBuild.currentResult}",
                        body: "Security build ${currentBuild.currentResult}.",
                        to: 'maxly746@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy to production...'
            }
        }
    }
}
