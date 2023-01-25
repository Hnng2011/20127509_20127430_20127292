pipeline {
    agent any
    
	environment {
	DOCKERHUB_CREDENTIALS=credentials('dockerhub')
    }
    

	stages {
		stage('Hello') {
			steps {
				echo 'Hello World'}}
	
		stage('Initialize'){
        			def dockerHome = tool '20127509'
        			env.PATH = "${dockerHome}/bin:${env.PATH}"}
		stage('Build Docker') {
			steps {
				sh 'docker build -t 20127509/testt .'}}

		stage('Login Docker') {
			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'}}
	
		stage('Push Docker') {
			steps {
				sh 'docker push 20127509/testt'}}
    }
}