pipeline {
    agent {
        node {
            label 'maven'
             }
          }

environment {
    PATH ="/opt/apache-maven-3.9.6/bin:$PATH"
}

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/go4paris/tweet-trend-new.git'
            }
        }
    }
    stages {
        stage("Build War") {
            steps {
                sh 'mvn package'
            }
        }
    }
