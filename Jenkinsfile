pipeline {
    agent {
        docker {
            image 'python:3.8.12'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'apt install -y python3.8-venv'
                sh '/usr/bin/python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requriment.txt'
                sh 'touch TheResult.exe' 
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'TheResult.exe', fingerprint: true
        }
    }
}

