pipeline {
    agent any

    stages {
        stage('Build the image') {
            steps {
                sh "pwd"
                sh "docker build -t lab01:10 ."
            }
        }
    }
}
