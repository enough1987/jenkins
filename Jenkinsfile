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
                mail to: 'tilgaaleksandr@gmail.com',
                     subject: "Successed Pipeline: ${currentBuild.fullDisplayName}",
                     body: "All is wrong with ${env.BUILD_URL}"
            }
            failure {
                echo 'This will run only if failed'
                mail to: 'tilgaaleksandr@gmail.com',
                     subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                     body: "Something is wrong with ${env.BUILD_URL}"
            }
        }
    }
}