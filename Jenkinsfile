pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build task is a stage where code is compiled into an executable format.'
                echo 'Maven Tool: '
                echo 'Automation tool for Java projects that manages dependencies, compiles code, runs tests.'
            }
        }

        stage('Test') {
            steps {
                echo 'Unit Testing'
                echo 'Ensures that individual components work correctly.'
                echo 'Mocha/Chai is a popular dependency used for unit testing in JavaScript/Node.js projects.'
                echo 'Integration Testing: '
                echo 'Different aspects of code work together as expected.'
                echo 'Postman: '
                echo 'Used for API testing, making it useful for integration tests involving RESTful services.'
            }
            post {
                success {
                    emailext subject: 'Success: Test Stage Email',
                              body: 'Stage 1: Build and Stage 2: Test is successful.',
                              to: 'atharvsbhandare@gmail.com',
                              attachLog: true
                }
                failure {
                    emailext subject: 'Failure: Test Stage Email',
                              body: 'Stage 1: Build or Stage 2: Test is unsuccessful.',
                              to: 'atharvsbhandare@gmail.com',
                              attachLog: true
                }
            }
        }

        // Define other stages here...
    }

    post {
        always {
            emailext attachLog: true,
                      body: "Build Log is attached.",
                      subject: "Build Log",
                      to: "atharvsbhandare@gmail.com"
        }
    }
}
