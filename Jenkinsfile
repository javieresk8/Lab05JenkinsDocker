pipeline {
    agent any
    environment {
        APPNAME = "myapitest"
        IMAGE = "myapitest"
        VERSION = 2
        REGISTRY = "javieresk8"
        DOCKER_HUB_LOGIN = credentials('dockerhub-javieresk8')
    }
    stages {
        stage('Build the image') {
            steps {
                sh "pwd"
                sh "docker build -t $REGISTRY/$IMAGE:$VERSION ."
            }
        }
        stage('Docker Push to Docker-hub'){
            steps{
                sh 'docker login --username=$DOCKER_HUB_LOGIN_USR --password=$DOCKER_HUB_LOGIN_PSW'
                sh 'docker push $REGISTRY/$APPNAME:$VERSION'
            }
        }
        stage('Deploy Image'){
            steps{
                sh 'docker rm -f $APPNAME'
                sh 'docker run -d --name $APPNAME$Env -p $PORT:$Port $REGISTRY/$IMAGE:$VERSION'
            }
        }
    }
}
