 pipeline
 {
	 //agent {docker {image 'maven:3.6.3'}}
	agent { docker { image 'node:13.8'} }
	  environment
	  {
	 	 dockerHome = tool 'myDocker'
	 	 mavenHome = tool 'myMaven'
	 	 PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	  }
	 
	stages
	{
		stage("Build")
		{
			steps
			{
				echo "First one"
				echo "Build"
				echo "$PATH"
				sh "mvn --version"
				echo "$env.BUILD_TAG"
	 			echo "$env.JOB_NAME"
 				echo "$env.BUILD_NUMBER"
 				echo "$env.BUILD_ID"

			}
		}
	}
	

	
	stage('Compile') 
	{
		steps

	 		{
	 			sh "mvn package"
	 		}
	}

	stage('Docker Build') 
	{
		steps
		{
			script
	 		{
		
	 				dockerImage = docker.build("girilv/giri-devops-microservice.git:$env.BUILD_TAG")
			}
		}
	}

	stage('Push Docker Image') 
	{
	 		steps
	 		{
	 			script
	 			{
	 				docker.withRegistry("","dockerhub") 				{
 					dockerImage.push();
 					dockerImage.push("latest")
					 
				}

			}
		}
	}		

	//  }
	//  post
	//  {
	// 	always
	// 	{
	// 		 echo "I run always"
	// 	}
	// 	success
	// 	{
	// 		echo "on success"
	// 	}
	// 	failure
	// 	{
	// 		echo "on failure"
	// 	}


			

	//  }
	
}
