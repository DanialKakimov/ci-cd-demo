pipeline {
    agent {
        docker {
            image 'python:3.10'
            args '-u'
        }
    }
    stages {
        stage('Run Tests') {
            steps {
                sh 'python -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
                sh './venv/bin/python -m unittest discover'
            }
        }
    }
}
