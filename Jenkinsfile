pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh'''
                docker build -t easy/sauce:latest .
                docker build -t easy/sauce2:latest . -f Dockerfile2
                '''
            }
        }
        stage('Test') { 
            steps {
                sh '''
                docker run easy/sauce2:latest
                '''
            }
        }
    }
}
