pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Tests') {
            steps {
                echo 'Running unit and integration tests...'
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
                echo 'Analyzing the code...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
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
                echo 'Deploying to staging...'
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
