pipeline {
    agent any
    tools {
        nodejs "NodeJS"   // Matches the name you gave in Global Tool Config
    }
    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('master') {
            steps {
                bat 'npm test'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
    }
}
