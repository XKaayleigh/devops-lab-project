pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('flask-app') {
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Run Tests') {
            steps {
                dir('flask-app') {
                    sh 'pytest'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                dir('flask-app') {
                    sh 'docker build -t flask-app:$BUILD_NUMBER .'
                }
            }
        }

    }
}