pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Example: sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example: sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code...'
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example: sh 'dependency-check.sh'
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
                // Example: sh 'run-selenium-tests.sh'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Example: sh 'scp -r target/ user@production-server:/path/to/deploy/'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Build ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                body: """Build ${currentBuild.fullDisplayName} completed with status: ${currentBuild.currentResult}.
                \nCheck console output at ${env.BUILD_URL} to view the results.""",
                to: 'developer@example.com',
                attachLog: true
            )
        }
    }
}
