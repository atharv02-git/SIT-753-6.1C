pipeline {
    agent any
    stages {
        // Stage 2: Build
        stage('Build') {
            steps {
                echo 'Building...'
            }
            post {
                success {
                    mail to: 'atharvsbhandare@gmail.com',
                    subject: 'build status email',
                    body: 'Build was successfull'
                }
            }
        }
        // Stage 3: Test
        stage('Test'){
            steps {
                echo 'Testing...'
            }
        }
        // Stage4: Deploying
        stage('Deploy'){
            steps{
                echo 'deploying...'
            }
        }
    }
}

