pipeline {
    agent any
    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                echo 'Build task is a stage where code is compiled, packaged, or transformed into a executable format. This process typically involves fetching source code, installing dependencies, compiling code, and running build-related tasks to produce artifacts like binaries, JAR files, or Docker images. The output from this stage is often used for further testing, deployment, or other post-build actions in the pipeline.'
                echo 'Maven: A build automation tool for Java projects that manages dependencies, compiles code, runs tests, and packages artifacts.'
                echo ' output from this stage is often used for further testing, deployment, or other post-build actions in the pipeline.'
            }
            // post {
            //     success {
            //         mail to: 'atharvsbhandare@gmail.com',
            //         subject: 'build status email',
            //         body: 'Build was successfull'
            //     }
            // }
        }
        // Stage 2: Unit and Integration Test
        stage('Test'){
            steps {
                echo 'unit and integration testing help ensure that individual components work correctly and that they integrate seamlessly to form a functional software system.'
                echo 'Mocha/Chai is a popular dependency used for unit testing in JavaScript/Node.js projects.'
                echo 'Postman: Primarily used for API testing, making it useful for integration tests involving RESTful services.'
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
        stage('Code Analysis'){
            steps{
                echo 'Code Analysis is basically a quality assurance stage for the code, just to make sure the code runs smoothly without any security vulnerabilities, bugs, etc. This stage improves code quality and reduces risks.'
                echo 'ESLint: A popular tool for analyzing JavaScript/TypeScript code for style issues, best practices, and potential bugs. It works well in Jenkins pipelines, especially for front-end projects.'
            }
        }
        // Stage 4: Security Scan
        stage('Security Scan'){
            steps{
                echo 'Security scan help identify vulnerablities, weaknesses, and other security risks in codebases.'
                echo 'Veracode: A type of scan which analyzes source code for security vulnerabilities without executing the code. It identifies common security flaws like SQL injection, cross-site scripting (XSS), and hardcoded secrets.'
            }
            post {
                success {
                    mail to: 'atharvsbhandare@gmail.com',
                    subject: 'Test Stage Email',
                    body: 'Stage 1: Build, Stage 2:, stage 3: Code Analysis, stage 4: Security Scan is successfull'
                }
                failure {
                    mail to: 'atharvsbhandare@gmail.com',
                    subject: 'Test Stage Email',
                    body: 'Stage 1: Build, Stage 2:, stage 3: Code Analysis, stage 4: Security Scan is unsuccessfull'
                }
            }
        }
        // Stage5: Deploying
        stage('Deploy to staging'){
            steps{
                echo 'Deployment refers to the process of deploying an application or service to a production or test environment.'
                echo 'AWS EC2 deploy: A deployment service provided by Amazon Web Services (AWS) that automates deploying applications to EC2 instances, Lambda functions, or other AWS resources. It integrates with Jenkins for automated deployment in cloud environments.'
            }
        }
        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging'){
            steps{
                echo 'Integration testing is a crucial step in the software development lifecycle, aiming to verify that different components or systems work together as expected.'
                echo 'Selenium: For automating browser-based tests, useful for testing web applications.' 
            }
        }
        // Stage 7: Deploy to production:
        stage{'Deploy to production'}
            echo 'Deploy the application to production server from staging server.'
            echo 'The same AWS EC2 instance can be used to deploy to the production server.'
    }
}

