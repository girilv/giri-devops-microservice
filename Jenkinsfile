 pipeline
 {
	 //agent any
	 agent { docker { image 'node:13.8'} }
	 stages
	 {
		stage('Build') 
		{
			steps
			{
				sh "node --version"
				echo "Build"
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
