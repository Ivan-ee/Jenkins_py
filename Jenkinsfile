pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo $(pwd)'
                sh 'python -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requirements.txt'
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