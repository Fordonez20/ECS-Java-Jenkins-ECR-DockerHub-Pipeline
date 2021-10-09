pipeline {
    agent { label "dep7agent"}
    
    environment{
        DOCKERHUB_CREDENTIALS_USR = "fordonez20"
        DOCKERHUB_CREDENTIALS_PSW = "0dec76c9-96ff-4a8a-8f81-6a526fb2e41c" //access token
    }
    stages {
        stage ('Build') {
            steps {
                sh 'docker build -t dep7jenkinstodocker .'
                
            }
        }
        stage ('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            
            }
        }
        stage ('Push') {
            steps {
                sh 'docker tag dep7jenkinstodocker:latest'
                sh 'docker push fordonez20:dep7jenkinstodocker:latest'
                
            }
        }
    }
}