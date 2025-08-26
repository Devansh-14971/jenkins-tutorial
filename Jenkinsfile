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
        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1' 
            }
                
        }
    }
    post {
        always {
            echo 'This runs always'
        }
        success {
            echo 'Runs on success'
        }
        failure {
            echo 'Runs on failure'
        }
        unstable {
            echo 'Runs if marked unstabe'
        } 
        changed {
            echo 'Runs if pipeline state changes'
            echo 'Like if unstable turns stable or failure turns success'
        }
    }
}
