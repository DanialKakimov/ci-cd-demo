pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/DanialKakimov/ci-cd-demo.git', branch: 'master'
            }
        }

        stage('Setup Python') {
            steps {
                // Создаем виртуальное окружение
                sh 'python3 -m venv venv || python -m venv venv'
                sh './venv/bin/pip install --upgrade pip'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh './venv/bin/python -m unittest discover -s tests'
            }
        }
    }
}
