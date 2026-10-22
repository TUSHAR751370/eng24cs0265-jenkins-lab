pipeline {
    agent {
        docker {
            image 'python:3.11-slim'
        }
    }
    stages {
        stage('Build / Lint') {
            steps {
                sh 'python3 -m py_compile calculator.py'
            }
        }
        stage('Test') {
            steps {
                sh 'pip install pytest && python3 -m pytest -v'
            }
        }
    }
}
