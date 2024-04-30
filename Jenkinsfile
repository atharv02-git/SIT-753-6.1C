pipeline {
    agent any
// Stages goes here
        stages {
            // Stage 1: Build
            stage('Build') {
                steps {
                    echo 'Build task is a stage where code is compiled into a executable format.'
                    echo 'Maven Tool: '
                    echo 'automation tool for Java projects that manages dependencies, compiles code, runs tests.'
                }
            }
            // Stage 2: Unit and Integration Test
            stage('Test') {
                steps {
                    echo 'Unit Testing'
                    echo 'Ensures that individual components work correctly.'
                    echo 'Mocha/Chai is a popular dependency used for unit testing in JavaScript/Node.js projects.'
                    echo 'Integration Testing: '
                    echo 'different aspects of code work together as expected.'
                    echo 'Postman: '
                    echo 'used for API testing, making it useful for integration tests involving RESTful services.'
                }
                post {
                    success {
                        mail to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Stage 1: Build and Stage 2: Test is successfull'
                    }
                    failure {
                        mail to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Stage 1: Build and Stage 2: Test is unsuccessfull'
                    }
                }
            }
            // Stage 3: Code Analysis
            stage('Code Analysis') {
                steps {
                    echo 'Code Analysis '
                    echo 'It is basically a quality assurance stage that improves code quality and reduces risks.'
                    echo 'ESLint:'
                    echo 'A tool for analyzing JavaScript code for style issues best practices and potential bugs.'
                }
            }
            // Stage 4: Security Scan
            stage('Security Scan') {
                steps {
                    echo 'Security scan help identify vulnerablities, weaknesses and other security risks in codebases.'
                    echo 'Veracode: '
                    echo 'A scan which analyzes source code for security vulnerabilities without executing the code.'
                    echo 'identifies common security flaws like SQL injection, XSS, and hardcoded secrets.'
                }
                post {
                    success {
                        mail to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Build, Test, Code Analysis, Security Scan is successfull'
                    }
                    failure {
                        mail to: 'atharvsbhandare@gmail.com',
                        subject: 'Test Stage Email',
                        body: 'Build, Test, Code Analysis, Security Scan is unsuccessfull'
                    }
                }
            }
            // Stage5: Deploying
            stage('Deploy to staging') {
                steps {
                    echo 'refers to the process of deploying an application to a production or test environment.'
                    echo 'AWS EC2 deploy: '
                    echo 'A deployment service provided by AWS that automates deploying applications to EC2 instances.'
                }
            }
            // Stage 6: Integration Tests on Staging
            stage('Integration Tests on Staging') {
                steps {
                    echo 'Integration testing is a crucial step in the software development lifecycle'
                    echo 'Aims to verify that different components or systems work together as expected.'
                    echo 'Selenium: For automating browser-based tests, useful for testing web applications.'
                }
            }
            // Stage 7: Deploy to production:
            stage ('Deploy to production') {
                steps {
                    echo 'Deploy the application to production server from staging server.'
                    echo 'The same AWS EC2 instance can be used to deploy to the production server.'
                }
        }
    }
}

