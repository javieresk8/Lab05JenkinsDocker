vpipeline {
    agent any
    environment {
        APPNAME = "myapitest"
        IMAGE = "myapitest"
        VERSION = 3
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
        
    }
}
