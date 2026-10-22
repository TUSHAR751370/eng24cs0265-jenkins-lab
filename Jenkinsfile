pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                sh 'ls -la'
            }
        }
        stage('Build / Lint') {
            steps {
                sh 'python3 -m py_compile calculator.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest -v'
            }
        }
        stage('Package / Artifact') {
            steps {
                sh 'tar -czvf app.tar.gz calculator.py test_calculator.py'
                archiveArtifacts artifacts: 'app.tar.gz', fingerprint: true
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
