pipeline {

    agent {
        docker {
            image 'maven:3-alpine'
        }
    }

    stages {
        stage('Compile sources') {
            steps {
                sh 'mvn clean compile'
            }
        }
	stage('Run unit tests'){
	    steps {
	        sh 'mvn test'
	    }
	}
	stage('Package artifact'){
	    steps {
		sh 'mvn package'
	    }
	}
    }

    post {
        always {
            archiveArtifacts 'build/libs/**/*.jar'

        } 
    }

}


