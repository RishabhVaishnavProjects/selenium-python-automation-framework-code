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
				git 'https://github.com/RishabhVaishnavProjects/selenium-python-automation-framework-code.git'
				script
				{
					bat(/pytest --browser chrome --url https:\/\/yatra.com --html=reportjenkins.html/)
				}
			
				step([$class : 'Publisher', reportFilenamePattern : '**/testing-results.xml'])
			}
		}
	}
}