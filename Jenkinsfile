pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                // Build automation tool: Maven
                // Maven is a build automation tool used primarily for Java projects. 
                // It helps compile, test, and package the code and manage dependencies.
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit...'
                // Test automation tool: JUnit
                // JUnit is a widely-used unit testing framework for Java. 
                // It provides a way to write and run tests to ensure the individual units of code are working correctly. 
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running code analysis on SonarQube...'
                // Code analysis tool: SonarQube
                // SonarQube is a static code analysis tool that measures code quality, detects bugs and vulnerabilities in various programming languages.
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP ZAP...'
                // Security scanning tool: OWASP ZAP (Zed Attack Proxy)
                // OWASP ZAP is a security testing tool that helps identify vulnerabilities in web applications by actively scanning for common security issues 
            }
            post {
                success {
                    mail to: "dinukadangampala@gmail.com",
                    subject: "Security Scan Staus Email",
                    body: "Security scan using OWASP ZAP was completed and successful!"
                    attachLog: True
                }
                failure {
                    mail to: "dinukadangampala@gmail.com",
                    subject: "Security Scan Staus Email",
                    body: "Security scan using OWASP ZAP has failed!"
                    attachLog: True
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server using AWS CLI...'
                // Deployment tool: AWS CLI (Command Line Interface)
                // AWS CLI allows for deploying files or applications to AWS resources like Amazon S3, EC2, etc.
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging using Seleniumg...'
                // Integration test tool: Selenium
                // Selenium is a popular open-source framework for automating web browsers. 
                // It enables running automated tests on web applications across different browsers and platforms.
            }
            post {
                success {
                    mail to: "dinukadangampala@gmail.com",
                    subject: "Integration Test Staus Email",
                    body: "Integration tests on staging using Selenium was successful!"
                    attachLog: True
                    
                }
                failure {
                    mail to: "dinukadangampala@gmail.com",
                    subject: "Integration Test Staus Email",
                    body: "Integration tests on staging using Selenium has failed. Please check the logs for info"
                    attachLog: True 
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server on AWS CLI...'
                // Deployment tool: AWS CLI (Command Line Interface)
            }
        }
    }
}
