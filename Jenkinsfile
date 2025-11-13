pipeline {
    agent {
        docker {
            image 'python:3.12'  // контейнер с Python 3.12
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/DanialKakimov/ci-cd-demo.git', branch: 'master'
            }
        }

        stage('Install Python') {
            steps {
                sh 'python -m venv venv'
                sh './venv/bin/pip install --upgrade pip'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh './venv/bin/python -m unittest discover'
            }
        }
    }
}