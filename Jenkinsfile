pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nehavc49/jenkins-101'
            }
        }

        stage('Setup Environment') {
            steps {
                sh '''
                    echo "Setting up Python environment..."
                    
                    # Install Python if not available
                    if ! command -v python3 &> /dev/null; then
                        echo "Python not found. Installing..."
                        apt update
                        apt install -y python3 python3-pip python3-venv
                    fi
                    
                    # Create and activate virtual environment
                    python3 -m venv venv
                    . venv/bin/activate
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    . venv/bin/activate
                    echo "Building the project..."
                    # Add your build commands here
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    . venv/bin/activate
                    echo "Running tests..."
                    # Add your test commands here
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    . venv/bin/activate
                    echo "Deploying the application..."
                    # Add your deployment commands here
                '''
            }
        }
    }

    post {
        always {
            sh '''
                echo "Cleaning up..."
                if [ -d "venv" ]; then
                    . venv/bin/activate && deactivate || true
                fi
            '''
        }
    }
}
