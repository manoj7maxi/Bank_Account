pipeline {
    agent any // Run on any available executor

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling code from Git...'
                // git 'https://github.com/user/repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling...'
                sh 'make' // Execute a shell command
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to Production...'
            }
        }
    }

    post { 
        always { 
            echo 'I will always run, regardless of success or failure!'
        }
        success {
            echo 'Build passed!'
        }
    }
}
