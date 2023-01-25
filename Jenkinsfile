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
			def dockerHome = tool '20127509'
        		env.PATH = "${dockerHome}/bin:${env.PATH}"
			steps {
				sh 'docker build -t 20127509/testt .'}}

		stage('Login Docker') {
			env.PATH = "${dockerHome}/bin:${env.PATH}"
			sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			steps {
				def dockerHome = tool '20127509'}}
        			
	
		stage('Push Docker') {
			env.PATH = "${dockerHome}/bin:${env.PATH}"
			sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			steps {
				sh 'docker push 20127509/testt'}}
    }
}