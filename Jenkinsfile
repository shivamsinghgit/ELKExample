node {
	//def application = "springbootapp"
	//def dockerhubaccountid = "sonal04"
	//stage('Clone repository') {
	//	checkout scm
	//}

	stage('Build image') {
		//app = docker.build("${dockerhubaccountid}/${application}:${BUILD_NUMBER}")
		app = docker.build("${application}:${BUILD_NUMBER}")
	}

	//stage('Push image') {
	//	withDockerRegistry([ credentialsId: "dockerHub", url: "" ]) {
	//	app.push()
	//	app.push("latest")
	//}
	//}

	stage('Deploy') {
		//sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ ${dockerhubaccountid}/${application}:${BUILD_NUMBER}")
		sh ("docker run -d -p 81:8080 -v /var/log/:/var/log/ ${application}:${BUILD_NUMBER}")
	}
	
	stage('Remove old images') {
		// remove docker pld images
		//sh("docker rmi ${dockerhubaccountid}/${application}:latest -f")
		sh("docker rmi ${application}:latest -f")
   }
}
