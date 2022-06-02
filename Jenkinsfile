pipeline{
	agent any
	stages{
		stage("Starting Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox" //sh for linux
			}
		}
		stage("Running Tests"){
			steps{
				bat "docker-compose up search-module1 search-module2 --no-color" //in jenkins there is no colors while running docker
			}
		}
		post{
			always{
				aschiveArtifacts artifacts: 'output/**'
				bat "docker-compose down" //stopping server
			}
		}	
	}
}