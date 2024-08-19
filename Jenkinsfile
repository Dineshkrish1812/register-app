pipeline{
	agent{label 'jenkins agent'}
	tools{
		jdk 'java17'
		maven 'maven3'
	}
	stages{
		stage("Cleanup workspace"){
			stpes{
			cleanWs()
			}
		}
		stage("Checkout from SCM"){
			steps{
				git branch:'main',credentialsId: 'github',url: 'https://github.com/Dineshkrish1812/register-app'
			}

		}
		stage("Build application"){
			steps{
				sh "mvn CLean package"
			}
		}
		stage("test application"){
			steps{
				sh "mvn test"
			}
		}
		
	}
}
