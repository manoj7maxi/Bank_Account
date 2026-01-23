pipeline {
    /* 'agent any' means this can run on any available build node. 
       Since yours is a Windows machine, it will use the Windows CMD.
    */
    agent any 

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling code from Git...'
                // The 'checkout scm' step is handled automatically by Jenkins 
                // when using a Pipeline from Git project.
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling...'
                /* We use 'bat' because 'sh' does not exist on Windows by default.
                   If you have a build tool like Maven or Gradle installed, 
                   you would use 'bat "mvn clean package"' here.
                */
                bat 'echo Directory Listing:'
                bat 'dir' 
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                // Example of a simulated test command
                bat 'echo Running tests... Success!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to Environment...'
                bat 'echo Deployment complete.'
            }
        }
    }

    /* Post actions run after the stages. 
       'always' runs regardless of success or failure.
    */
    post {
        always {
            echo 'Cleanup or Final Reporting...'
        }
        success {
            echo 'Build was successful! Sending notification...'
        }
        failure {
            echo 'Build failed. Checking logs...'
        }
    }
}
