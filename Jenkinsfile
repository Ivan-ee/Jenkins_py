pipeline {
    agent any
    stages {
    stage('init') {
            steps {
                sh '/usr/bin/python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requriment.txt'
            }
        }
        stage('Build') {
            steps {
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