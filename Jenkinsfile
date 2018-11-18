pipeline {
    agent { 
        docker { 
            image 'node:8'
            args '-p 3000:3000'
        } 
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
        stage('build') {
            steps {
                sh 'npm install'
            }
        }
        post {
            success {
                echo 'This will run only if successful'
            }
            failure {
                echo 'This will run only if failed'
            }
        }
    }
}