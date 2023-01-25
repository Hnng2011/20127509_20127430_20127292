pipeline {
    agent any
    enviroment {
	DOCKERHUB_CREDENTIALS=credentials('dockerhub')
    }
    

	stages {
		stage('Hello') {
			steps {
				echo 'Hello World'}}
	
	
	stage('Build Docker') {
		sh 'docker build -t 20127509/testt .'
        }

	stage('Login Docker') {
		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'            
        }
	
	stage('Push Docker') {
            sh 'docker push 20127509/testt'
        }
    }
}