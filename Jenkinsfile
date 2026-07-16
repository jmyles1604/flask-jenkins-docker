pipeline {
    agent any

    stages {
        stage('Clean Up') {
            steps {
                sh 'docker rm -f flask-app || true'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:5500 --name flask-app flask-app:latest'
            }
        }
    }
}
