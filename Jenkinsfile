pipeline {
    agent any
    stages {
        stage('Docker Test Execution') {
            steps {
                sh 'docker run --rm -v $WORKSPACE:/app -w /app python:3.11-slim sh -c "pip install pytest && python3 -m pytest -v"'
            }
        }
    }
    post {
        always {
            echo 'Docker pipeline execution finished.'
        }
    }
}
