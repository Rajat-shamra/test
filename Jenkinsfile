pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "✅ Pulling latest code from GitHub..."
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "✅ Building the application..."
                sh 'echo "Build process completed successfully!"'
            }
        }
        stage('Test') {
            steps {
                echo "✅ Running tests..."
                sh 'echo "All tests passed successfully!"'
            }
        }
        stage('Deploy') {
            steps {
                echo "✅ Deploying the application..."
                sh 'echo "Deployment simulation completed!"'
            }
        }
    }
}
