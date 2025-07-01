pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/your-username/portfolio-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('my-portfolio')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop my-portfolio || true'
                sh 'docker rm my-portfolio || true'
                sh 'docker run -d --name my-portfolio -p 8082:80 my-portfolio'
            }
        }
    }
}
