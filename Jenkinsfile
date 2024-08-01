pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-html-app')
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('my-html-app').inside {
                        sh 'echo "Testing HTML app"'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.image('my-html-app').inside {
                        sh 'echo "Deploying HTML app"'
                    }
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}

