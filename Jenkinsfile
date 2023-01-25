pipeline {
    agent any
    
	environment {
	DOCKERHUB_CREDENTIALS=credentials('dockerhub')
    }
    

	stages {
		stage('Hello') {
			steps {
				echo 'Hello World'}}
	
		stage('Build Docker') {
			steps {
				sh 'docker build -t 20127509/testt .'}}

		stage('Login Docker') {
			steps {
				def dockerHome = tool '20127509'}}
        			
	
		stage('Push Docker') {
			steps {
				sh 'docker push 20127509/testt'}
    }
}