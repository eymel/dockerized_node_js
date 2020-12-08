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
                sh 'docker build -t nodebackend .'
            }
            
        }
        stage('Docker run') {
           steps {
                sh 'docker run --rm  -d -p 9060:8080 -v `pwd -W`:/home/node/app -v node_modules:/home/node/app/node_modules --name myNodeServer  nodebackend '
            }
        }
        
    }
}