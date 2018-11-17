pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
    }
    stages {
        stage('Install dependencies') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}


