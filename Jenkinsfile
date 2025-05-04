pipeline {
    agent {
        docker {
            image 'python:3-slim'
            args '--network=host -v /tmp:/tmp'
        }
    }
    stages {
        stage('Setup') {
            steps {
                checkout scm
                sh 'pip install -r requirements.txt'  // Install dependencies
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'  // Example if you have tests
            }
        }
        stage('Run') {
            steps {
                sh 'python3 helloworld.py'
            }
        }
    }
}
