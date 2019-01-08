pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    options {
        checkoutToSubdirectory('essential-path') 
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('start') {
            steps {
                echo env
                sh 'ls'
                script {
                  getTag()
                }
                echo 'starting'
                dir('manong') {
                    git url: 'https://github.com/geekchow/manong.git'
                }
                sh 'ls'
                sh 'ls manong'
                sh 'ls essential-path'
            }
        }    
    }
}


def getTag() {
  tag = sh(script: 'cd essential-path && git status', returnStdout:true).trim()
  echo "${tag}"
}
