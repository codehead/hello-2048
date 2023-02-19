pipeline {
    agent any
    
    options {
        timestamps()
        ansiColor('xterm')
    }

    stages {
        stage('Build') {
            steps {
                sh 'docker-compose build'
            }
        }
        stage('Tag') {
            steps {
                echo 'Tag image, repo'
            }
        }
        stage('Deploy') {
            steps {
                sh '''docker-compose up -d
                docker-compose logs -t --tail=10 
                '''
            }
        }
    
    }
}
