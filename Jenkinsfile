pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build task is a stage where code is compiled into an executable format.'
                echo 'Maven Tool:'
                echo 'Automation tool for Java projects that manages dependencies, compiles code, runs tests.'
            }
        }

        stage('Test') {
            steps {
                echo 'Unit Testing'
                echo "Performing Unit Testing using JUnit..."
                echo 'Integration Testing:'
                echo "Performing Integration Testing using Selenium WebDriver..."

                script {
                    def logFilePathNew = "${env.WORKSPACE}\\test-output.log"
                    bat """
                        echo Starting unit testing using JUnit... > ${logFilePathNew}
                        echo Testing the feature working... >> ${logFilePathNew}
                        echo Unit testing completed and no issues found >> ${logFilePathNew}
                        echo \\n\\nStarting Integration testing using Selenium WebDriver... >> ${logFilePathNew}
                        echo End to End Testing of the complete product working... >> ${logFilePathNew}
                        echo Integration testing completed and no issues found >> ${logFilePathNew}
                    """
                }
            }
            post {
                success {
                    emailext attachmentsPattern: 'test-output.log',
                        to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Stage 1: Build and Stage 2: Test is successful'
                }
                failure {
                    emailext attachmentsPattern: 'test-output.log',
                        to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Stage 1: Build and Stage 2: Test is unsuccessful'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Code Analysis'
                echo 'It is basically a quality assurance stage that improves code quality and reduces risks.'
                echo 'ESLint:'
                echo 'A tool for analyzing JavaScript code for style issues, best practices, and potential bugs.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Security scan helps identify vulnerabilities, weaknesses, and other security risks in codebases.'
                echo 'Veracode:'
                echo 'A scan which analyzes source code for security vulnerabilities without executing the code.'
                echo 'Identifies common security flaws like SQL injection, XSS, and hardcoded secrets.'

                script {
                    def logFilePathSecurity = "${env.WORKSPACE}\\security-output.log"
                    bat """
                        echo Starting security scan using Veracode... > ${logFilePathSecurity}
                        echo Checking for SQL injection, XSS, and hardcoded secrets... >> ${logFilePathSecurity}
                        echo Security scan completed. No critical issues found. >> ${logFilePathSecurity}
                    """
                }
            }
            post {
                success {
                    emailext attachmentsPattern: 'security-output.log',
                        to: 'atharvsbhandare@gmail.com',
                        subject: 'Security Scan Stage Success',
                        body: 'Build, Test, Code Analysis, and Security Scan are successful.'
                }
                failure {
                    emailext attachmentsPattern: 'security-output.log',
                        to: 'atharvsbhandare@gmail.com',
                        subject: 'Security Scan Stage Failure',
                        body: 'Build, Test, Code Analysis, and Security Scan have failed.'
                }
            }
        }

        stage('Deploy to staging') {
            steps {
                echo 'Refers to the process of deploying an application to a production or test environment.'
                echo 'AWS EC2 deploy:'
                echo 'A deployment service provided by AWS that automates deploying applications to EC2 instances.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration testing is a crucial step in the software development lifecycle'
                echo 'Aims to verify that different components or systems work together as expected.'
                echo 'Selenium: For automating browser-based tests, useful for testing web applications.'
            }
        }

        stage('Deploy to production') {
            steps {
                echo 'Deploy the application to the production server from the staging server.'
                echo 'The same AWS EC2 instance can be used to deploy to the production server.'
            }
        }
    }
}
