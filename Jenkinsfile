pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // Build automation tool: Maven
                // Example command: mvn clean install
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Test automation tool: JUnit
                // Example command: mvn test
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...'
                // Code analysis tool: SonarQube
                // Example command: mvn sonar:sonar
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Security scanning tool: OWASP ZAP
                // Example command: zap-baseline.sh -t <target-url> -r report.html
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
                // Deployment tool: AWS CLI
                // Example command: aws s3 sync <local-dir> s3://<bucket-name>
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Integration test tool: Selenium
                // Example command: mvn integration-test
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
                // Deployment tool: AWS CLI
                // Example command: aws s3 sync <local-dir> s3://<bucket-name>
            }
            post {
                success {
                    mail to: "dinukadangampala@gmail.com",
                    subjectL "Build Staus Email",
                    body: "Build was successful!"
                }
            }
        }
    }
}

