pipeline {
    agent any
    

	stages {
		stage('Hello') {
			steps {
				echo 'Hello World'}}
	
		stage('Build & Push docker') {
			steps {
				withDockerContainer('jenkins:jenkins:lts') {
				sh 'docker build -t 20127509/testt .'
				sh 'docker push 20127509/testt'}}}
        			
}
}