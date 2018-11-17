pipeline {

    agent {
        docker {
            image 'maven:3-alpine'
        }
    }

    stages {
        stage('Compile sources') {
            steps {
                sh 'mvn -q clean compile'
            }
        }
	stage('Run unit tests'){
	    steps {
	        sh 'mvn -q test'
	    }
	}
	stage('Package artifact'){
	    steps {
		sh 'mvn -q package'
	    }
	}
    }

    post {
        always {
            archiveArtifacts '**/*.jar'
        } 
    }

}


