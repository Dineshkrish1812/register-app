pipeline{
	agent{label 'jenkins agent'}
	tools{
		jdk 'java17'
		maven 'maven3'
	}
	stages{
		stage("Cleanup workspace"){
			steps{
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
				sh "mvn Clean package"
			}
		}
		stage("test application"){
			steps{
				sh "mvn test"
			}
		}
		
	}
}
