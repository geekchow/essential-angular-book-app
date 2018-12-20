pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    options {
        checkoutToSubdirectory('essential-path') 
        disableConcurrentBuilds()
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('start') {
            steps {
                sh 'ls'
                echo 'starting'
                dir('manong') {
                    git url: 'https://github.com/geekchow/manong.git'
                }
                sh 'ls'
            }
        }
        
    }
}