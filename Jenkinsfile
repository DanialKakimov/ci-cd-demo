pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/DanialKakimov/ci-cd-demo.git'
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

