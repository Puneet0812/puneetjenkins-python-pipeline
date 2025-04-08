pipeline {
    agent {
        docker {
            image 'python:3.11'     // Official Python image
            args '-u root'          // Run as root to avoid permission issues
        }
    }
    stages {
        stage('Install dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run tests') {
            steps {
                sh 'pytest'
            }
        }
        stage('Package with PyInstaller') {
            steps {
                sh 'pip install pyinstaller'
                sh 'pyinstaller --onefile sources/add2vals.py'
            }
        }
        stage('Archive Build') {
            steps {
                archiveArtifacts artifacts: 'dist/add2vals', onlyIfSuccessful: true
            }
        }
    }
}
