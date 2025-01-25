pipeline {
    agent any
    stages {
        stage('git-code-download') {
            steps {
                echo "Download code from Git"
                git branch: 'main', url: 'https://github.com/Vansh-Umraliya/maven-jenkins6.git'
            }
        }
        stage('create-docker-image') {
            steps {
                sh '''
                docker build -t  vansh741/javawebapp:${BUILD_NUMBER} .
                docker tag vansh741/javawebapp:${BUILD_NUMBER} vansh741/javawebapp:latest
                docker push vansh741/javawebapp:${BUILD_NUMBER}
                docker push vansh741/javawebapp:latest
                '''
            }
        }
    }
}
