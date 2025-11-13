pipeline {
    agent {
        docker {
            image 'python:3.10' // готовый образ с Python
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/DanialKakimov/ci-cd-demo.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'python -m venv venv'
                sh '. venv/bin/activate && pip install --upgrade pip'
                sh '. venv/bin/activate && pip install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && pytest || true'
            }
        }
    }
}


