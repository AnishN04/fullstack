pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('master') {
            steps {
                dir('frontend') {
                    bat 'npm test -- --passWithNoTests'
                }
            }
        }

        stage('Build') {
            steps {
                dir('frontend') {
                    bat 'npm run build'
                }
            }
        }
    }
}
