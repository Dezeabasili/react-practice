pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo 'Hello World'
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('with docker') {
            agent {
                docker {
                    image 'node:22-alpine'
                    reuseNode true
                }
            }
            steps {
                sh ''' 
                    echo 'Using Docker'
                    npm --version
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}