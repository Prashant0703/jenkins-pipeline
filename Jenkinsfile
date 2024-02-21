node {
	stage("TEST") {
		echo ("HELLO")
	}
	stage("RUN JOB") {
			build job: "template-runner"
			parameters: [
			 string(name: "Name", value: "Chetna"),
			]
	}
}

