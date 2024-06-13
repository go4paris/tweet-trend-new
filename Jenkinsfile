pipeline {
    agent {
        node {
            label 'maven'
             }
          }



    stages {
        stage("Checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/go4paris/tweet-trend-new.git'
            }
        }
    }

environment {
    PATH ="/opt/apache-maven-3.9.6/bin:$PATH"
}

    stages {
        stage("Build War") {
            steps {
                sh 'mvn package'
            }
        }
    }
}
   