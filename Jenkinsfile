pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Build Application') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t login-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8080:8080 login-app'
            }
        }

    }
}
