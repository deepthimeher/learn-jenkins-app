pipeline {
    agent any

    stages{
        stage ('Test') {
            steps {
                sh '''
                ls /workspaces/learn-jenkins-app/build/index.html
                '''

            }
        }
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
                    npm ci
                    npm run build
                    ls -la
                    '''
                }
               
            }
        }
    }
