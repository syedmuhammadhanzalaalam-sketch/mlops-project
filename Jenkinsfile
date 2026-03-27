pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/syedmuhammadhanzalaalam-sketch/mlops-project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d --name myapp -p 80:80 app'
            }
        }
    }
}
