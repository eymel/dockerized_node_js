pipeline {
    agent {
        docker {
            image 'docker'
            args '-v /var/run/docker.sock:/var/run/docker.sock --privileged'
        }
    }
    stages {
        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker-compose build'
            }
            
        }
        stage('Docker run') {
           steps {
                sh 'docker-compose up -d'
            }
        }
        
    }
}