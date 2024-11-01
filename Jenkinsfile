

pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                echo "without doccker"
                ls -la 
                touch container-no.txt
                '''
            }
        }
        
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            
            steps {
                sh '''
                sh 'echo "with docker"'
                ls -la
                touch container-yes.txt
                '''
            }
        }
    }
}
 