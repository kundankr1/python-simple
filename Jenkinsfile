pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/<YOUR-USERNAME>/<YOUR-REPO>.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-jenkins-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                  docker rm -f python-app || true
                  docker run -d --name python-app python-jenkins-app
                '''
            }
        }
    }
}
