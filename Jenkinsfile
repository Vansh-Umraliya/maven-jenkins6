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
                docker build -t webapp .
                docker run -d -p 8081:8080 webapp
                '''
            }
        }
    }
}
