pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Run tests') {
            steps {
                sh 'pytest'
            }
        }
        stage('Package with PyInstaller') {
            steps {
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
