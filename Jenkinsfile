pipeline {
    agent any
    stages {
        stage('Run Python') {
            steps {
                script {
                    docker.image('python:3.12').inside {
                        sh 'python -m venv venv'
                        sh 'venv/bin/pip install -r requirements.txt'
                        sh 'venv/bin/python -m unittest discover'
                    }
                }
            }
        }
    }
}

