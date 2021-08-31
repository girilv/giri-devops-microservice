 pipeline
 {
	 agent any
	 //agent { docker { image 'node:13.8'} }
	 environment
	 {
		 dockerHome = tool 'myDocker'
		 mavenHome = tool 'myMaven'
		 PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	 }
	 
	 stages
	 {
		stage('Build') 
		{
			steps
			{
				echo "mvn --version"
				echo "docker version"
				echo "Build"
				echo "$PATH"
				echo "$env.BUILD_TAG"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_NUMBER"
				echo "$env.BUILD_ID"

			}
		}
		stage('Test') 
		{
			steps
			{
				echo "Test"
			}
		}
		stage('Integration Test') 
		{
			steps
			{
				echo "Integration Test"
			}
		}	 
	 }
	 post
	 {
		always
		{
			 echo "I run always"
		}
		success
		{
			echo "on success"
		}
		failure
		{
			echo "on failure"
		}


			

	 }
	
}
