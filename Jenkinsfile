pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "Pulling latest code from GitHub..."
                checkout scm
            }
        }
        stage('Deploy to Apache') {
            steps {
                echo "Deploying index.html to Ubuntu Apache..."
                // SSH to Ubuntu server and copy file to /var/www/html/
                sh '''
                # Install Apache if not installed
                if ! dpkg -l | grep -q apache2; then
                  sudo apt-get update
                  sudo apt-get install -y apache2
                fi

                # Copy index.html to Apache directory
                sudo cp index.html /var/www/html/index.html

                # Restart Apache
                sudo systemctl restart apache2
                '''
            }
        }
    }
}
