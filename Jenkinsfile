pipeline {
    agent any

    stages {
	stage('Preparation') {
	    steps {
                cleanWs()
                checkout scm
	    }
	}
        stage('Creating a Docker image') {
            steps {
		echo "Building.."
                sh 'docker build -t apni-poetry-image .'
            }
        }
        stage('Creating a Docker container') { 
            steps {
                sh 'docker run -d --name "poetry_container" -p 88:80 apni-poetry-image'
            }
        }
    }
}
