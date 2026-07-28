pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                echo 'checking out code from Github...'
                checkout scm
            }
        }
        stage('Intsall Dependencies') {
            steps {
                echo "Installing dependencies..."
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                echo "Rinning tests..."
                sh 'pytest'
            }
        }
        stage('Build') {
            steps {
                echo "Building the application..."
                sh 'python appp.py'
            }
        }
    }
}
