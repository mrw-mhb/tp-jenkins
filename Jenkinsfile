pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                bat 'docker run --rm node:26.13.0-alpine3.24 node --eval "console.log(process.arch,process.platform)"'
            }
        }
    }
}
