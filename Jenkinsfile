pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'echo Building...'  // Use "bat" for Windows batch commands
            }
        }
    }
}

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/nehavc49/jenkins-101'
            }
        }

        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }

        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}

