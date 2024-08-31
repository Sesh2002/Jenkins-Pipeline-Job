pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Specify the build tool, e.g., Maven
                // sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Specify test tools, e.g., JUnit
                // sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality...'
                // Specify code analysis tool, e.g., SonarQube
                // sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Specify security scan tool, e.g., OWASP ZAP
                // sh 'zap-baseline.py -t http://localhost'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                // Specify deployment method, e.g., using AWS CLI
                // sh 'aws deploy --application-name myApp --deployment-group-name staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Run integration tests on staging
                // sh 'mvn integration-test -Pstaging'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                // Specify production deployment method
                // sh 'aws deploy --application-name myApp --deployment-group-name production'
            }
        }
    }
    post {
        always {
            emailext(
                to: 'seshinimanushika20021114@gmail.com', // Updated email address
                subject: "Pipeline ${currentBuild.fullDisplayName}",
                body: """Pipeline ${currentBuild.fullDisplayName} finished with status ${currentBuild.currentResult}.
                         Check the Jenkins console output for details.""",
                mimeType: 'text/html',
                attachLog: true // This will attach the console log to the email
            )
        }
    }
}
