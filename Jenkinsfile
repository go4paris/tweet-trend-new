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
        stage("Checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/go4paris/tweet-trend-new.git'
            }
        }
    

        stage("Build War") {
            steps {
                sh 'mvn package'
            }
        }
    

        stage('SonarQube analysis') {
            environment {
                   scannerHome = tool 'sonar-scanner'
                }
                steps{
                     withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
                      sh "${scannerHome}/bin/sonar-scanner"
                       }
                    }
        }



    }
}
   