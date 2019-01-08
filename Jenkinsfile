pipeline {

    agent {
        docker {
            image 'maven:3-alpine'
        }
    }

    stages {
        stage('Compile sources') {
            steps {
                sh 'mvn -B clean compile'
            }
        }
	stage('Run unit tests'){
	    steps {
	        sh 'mvn -B test'
	    }
	}
	stage('Package artifact'){
	    steps {
		sh 'mvn -B package'
	    }
	}
    }

    post {
        always {
            archiveArtifacts 'target/*.jar'
        } 
    }

}


