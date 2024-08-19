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
				git branch: 'main', changelog: false, credentialsId: 'github', poll: false, url: 'https://github.com/Dineshkrish1812/register-app.git'
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
