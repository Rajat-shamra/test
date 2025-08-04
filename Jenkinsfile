pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "✅ Pulling latest code from GitHub..."
                checkout scm
            }
        }
        stage('Deploy to Apache') {
            steps {
                echo "✅ Deploying website to Apache..."
                sh '''
                # Ensure Apache is installed
                if ! dpkg -l | grep -q apache2; then
                    echo "Installing Apache..."
                    sudo apt-get update
                    sudo apt-get install -y apache2
                fi

                # Copy the HTML file to Apache root
                sudo cp index.html /var/www/html/index.html

                # Restart Apache service
                sudo systemctl restart apache2
                echo "✅ Deployment completed!"
                '''
            }
        }
    }
}
