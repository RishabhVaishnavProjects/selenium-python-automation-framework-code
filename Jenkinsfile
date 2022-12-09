pipeline
{
	agent
	{
		node 
		{
			label 'master'
		}
	}
	
	options
	{
		timestamps()
	}
	
	stages
	{
		stage("Checkout, Build and Test")
		{
			steps
			{
				checkout scm
				script
				{
					bat(/pytest --browser chrome --url https:\/\/yatra.com --html=reportjenkins.html/)
				}
			
				step([$class : 'Publisher', reportFilenamePattern : '**/testing-results.xml'])
			}
		}
	}
}