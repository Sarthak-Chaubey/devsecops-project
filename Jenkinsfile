pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning project...'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devsecops-project .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3000:3000 devsecops-project'
            }
        }
    }
}