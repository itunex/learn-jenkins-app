pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'nodejs:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -al
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}