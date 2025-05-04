pipeline {
    agent {
        docker {
            image 'python:3-slim'
            args '--network=host -v /tmp:/tmp'
        }
    }
    stages {
        stage('Info') {
            steps {
                echo 'Name: Anya Kalluri'
                echo 'Roll Number: se22ucse033'
            }
        }
        stage('Setup') {
            steps {
                checkout scm
                sh 'pip install -r requirements.txt'
                sh 'git branch -a'  // Example additional command
            }
        }
        stage('Run') {
            steps {
                sh 'python3 helloworld.py'
            }
        }
    }
}
