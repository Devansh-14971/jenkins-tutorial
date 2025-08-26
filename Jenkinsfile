pipeline {
    agent { docker { image 'python:3.13.7-alpine3.22' } }
    stages {
        stage('build') {
            steps {
                timeout(time: 3, unit: 'MINUTES'){
                    retry(5){
                        sh 'python --version'
                    }
                }
            }
        }
    }
}
