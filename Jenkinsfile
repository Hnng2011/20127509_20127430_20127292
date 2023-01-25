pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

     stages {
        stage('Push docker') {
            steps {
                withDockerRegistry(credentialsId: 'docker', url: 'https://index.docker.io/v1/') {
			sh label: '', script: 'docker build -t 20127509/test'		    
			sh label: '', script: 'docker push 20127509/test'
			}
            }
        }
    }
}