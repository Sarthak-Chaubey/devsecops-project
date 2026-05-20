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

        stage('Stop Old Container') {
            steps {
                bat 'docker stop devsecops-container || exit 0'
                bat 'docker rm devsecops-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d --name devsecops-container -p 3000:3000 devsecops-project'
            }
        }
    }
}