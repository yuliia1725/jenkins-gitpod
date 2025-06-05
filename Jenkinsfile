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
                bat '''
                    curl -L -o semgrep.exe https://github.com/returntocorp/semgrep/releases/latest/download/semgrep-windows-x86_64.exe
                    semgrep.exe scan --config auto . || echo Semgrep scan completed with non-zero exit code
                '''
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
