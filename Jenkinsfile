pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run tests') {
            steps {
                sh 'pytest test_calculator.py'
            }
        }

        stage('Package with PyInstaller') {
            steps {
                sh 'pip install pyinstaller'
                sh 'pyinstaller --onefile calculator.py'
            }
        }

        stage('Archive Build') {
            steps {
                archiveArtifacts artifacts: 'dist/*', fingerprint: true
            }
        }
    }
}
