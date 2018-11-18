pipeline {
    agent { 
        docker { 
            image 'node:8' 
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
                sh 'npm --version'
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