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
				def dockerHome = tool '20127509'
        			env.PATH = "${dockerHome}/bin:${env.PATH}"
				sh 'docker build -t 20127509/testt .'}}

		stage('Login Docker') {
			steps {
				def dockerHome = tool '20127509'
        			env.PATH = "${dockerHome}/bin:${env.PATH}"
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'}}
	
		stage('Push Docker') {
			steps {
				def dockerHome = tool '20127509'
        			env.PATH = "${dockerHome}/bin:${env.PATH}"
				sh 'docker push 20127509/testt'}}
    }
}