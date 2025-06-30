pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/donidOns/php-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'echo "No composer.json, skip install dependencies"'
            }
        }
        stage('Run Unit Test') {
            steps {
                sh 'echo "Simulasi unit test PHP (dummy)"'
            }
            post {
                success {
                    echo 'Tes berhasil!'
                }
                failure {
                    echo 'Tes gagal!'
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t php-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8081:80 php-app'
            }
        }
    }
}
