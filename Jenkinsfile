pipeline {
    agent {
        docker {
            image 'python:3.8.12'

            args "-u root"
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo $(pwd)' 
                sh 'python -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requirements.txt'
                sh 'python main.py'
                sh 'touch app.exe'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'app.exe', fingerprint: true
        }
    }
}