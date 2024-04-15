pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com//https://github.com/Sukhmnn13/dev-ops-assg3/tree/main.git'
            }
        }
        stage('Build image') {
            steps {
                sh 'docker build -t my-custom-image .'
            }
        }
        stage('Deploy image') {
            steps {
                sh 'docker run -d -p 8080:8080 my-custom-image'
            }
        }
    }
}
