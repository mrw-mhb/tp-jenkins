pipeline {
    agent any
    stages {
        /* "Build" and "Test" stages omitted */

        stage('Deploy - Staging') {
            steps {
                bat 'deploy.bat staging'
                bat 'run-smoke-tests.bat'
            }
        }

        stage('Sanity check') {
            steps {
                input "Does the staging environment look ok?"
            }
        }

        stage('Deploy - Production') {
            steps {
                bat 'deploy.bat production'
            }
        }
    }
}
