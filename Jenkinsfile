pipeline {
    agent any
    environment {
        DIRECTORY_PATH = '/path'
        TESTING_ENVIRONMENT = 'test_environment'
        PRODUCTION_ENVIRONMENT = 'production_environment'
    }
    stages {
        stage('Build') {
            steps {
                echo 'fetch the source code from the directory path: $DIRECTORY_PATH..'
                echo 'Is where the codes and configurations are developed'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'unit tests is to check that your code works as expected'
                echo 'integration testing involves evaluating how your software interacts with other software or functions, ensuring that it works well         in conjunction with them'
            }
            post {
                success {
                    emailext(
    attachLog: true,
    subject: 'Unit and Integration Tests Status Email',
    body: 'Unit and Integration Tests was successful!',
    to: 'atharvsbhandare@gmail.com'
    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'We use CodeClimate for test automation at this stage. This tool will gives you insights on your code complexity, redundancy and         test coverage.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'In this stage, a security scan tool is used which is ConnectWise, to assess any cyber attacks. Deploy the application to a testing     This is used for quick indentification threat. Testing environment: $TESTING_ENVIRONMENT...'
            }
            post {
                success {
                    emailext(
    attachLog: true,
    subject: 'Security Scan Status Email',
    body: 'Security Scan was successful!',
    to: 'atharvsbhandare@gmail.com'
    )
                }
            }
        }
        stage('Integration Tests') {
            steps {
                sleep 10
                echo 'The data is feeding from the system.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'deploy the code to production environment: AWS EC2...'
            }
        }
    }
}
