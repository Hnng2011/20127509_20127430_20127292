pipeline {
    agent any
    

	stages {
		stage('Hello') {
			steps {
				echo 'Hello World'}}
	
		stage('Build & Push docker') {
			steps {
				withDockerRegistry(credentialsId: 'dockerHub', url: 'https://index.docker.io/v1/'){ 
				sh 'docker build -t 20127509/testt .'}
				sh 'docker push 20127509/testt'}}}
        			
}
}