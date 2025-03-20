pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci // like npm install (get node modules, but for a CI server)
                    npm run build
                    ls -la
                '''
            }
        }
    }
}