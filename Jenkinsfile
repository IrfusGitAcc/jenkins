pipeline {
    agent {
        docker { image 'python:3.12-slim' }
    }
    stages {
        stage('Build') {
            steps {
                echo "Build number ${env.BUILD_NUMBER}"
                sh 'python3 --version'
                sh 'pip install --user -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest test_app.py'
            }
        }
        stage('Package') {
            steps {
                sh 'echo packaging...'
            }
        }
    }
    post {
        always {
            echo "Pipeline finished with status: ${currentBuild.currentResult}"
        }
    }
}
