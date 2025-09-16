pipeline {
    agent any

    stages {
        stage('Backend Install & Build') {
            steps {
                dir('backend') {
                    bat 'npm install'
                    bat 'npm run build'   // remove this if your backend doesn’t need build
                }
            }
        }

        stage('Frontend Install & Build') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                    bat '''
                        set "CI="
                        npm run build
                    '''
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished!'
        }
        success {
            echo 'Build successful, archiving artifacts...'
            archiveArtifacts artifacts: 'frontend/build/**', fingerprint: true
        }
        failure {
            echo 'Build failed!'
        }
    }
}
