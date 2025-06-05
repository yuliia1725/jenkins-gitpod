pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }
        stage('SAST Scan (Semgrep)') {
            steps {
                sh 'curl -L https://github.com/returntocorp/semgrep/releases/latest/download/semgrep-linux -o semgrep'
                sh 'chmod +x semgrep'
                sh './semgrep scan --config auto . || true'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying project...'
            }
        }
    }
}
