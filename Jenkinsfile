pipeline {
    agent any

    stages {
        stage('Build the image') {
            steps {
                sh "pwd"
                sh "docker build -t lab01:1.0 ./Lab01"
            }
        }
    }
}
