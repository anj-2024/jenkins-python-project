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
                sh ''' python3 -m venv venv 
                .venv/bin/activate/
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }
        stage('Run Tests') {
            steps {
                echo "Rinning tests..."
                sh '''
                .venv/bin/activate
                pytest
                '''
            }
        }
        stage('Build') {
            steps {
                echo "Building the application..."
                sh 'python3 appp.py'
            }
        }
    }
}
