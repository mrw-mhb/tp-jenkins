pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat '''
                    if not exist build\\libs mkdir build\\libs
                    echo application > build\\libs\\app.jar
                '''
            }
        }
        stage('Test') {
            steps {
                bat '''
                    if not exist build\\reports mkdir build\\reports
                    type tests\\TEST-demo.xml > build\\reports\\TEST-demo.xml
                '''
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
}
