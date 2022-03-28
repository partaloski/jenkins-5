node{
	def app
	
	stage('Clone repository') {
	
	
		checkout scm
	}
	
	stage('Push image') {
	
		docker.withRegistry('https://registry.hub.docker.com', 'git'){
			app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
			app.push("${env.BRANCH_NAME}-latest")
			//To signal that a new version is pushed.
		}
	}
}