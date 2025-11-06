pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/sample-webapp.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example: if using Node.js
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example: run tests
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Example deployment step
                sh 'scp -r * user@server:/var/www/html/'
            }
        }
    }
}
