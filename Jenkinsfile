pipeline{
	agent any
	stages{
		stage("Pulling Latest Image"){
			steps{
				bat "docker pull dgdocker1987/selenium-docker"  // to update image if there are any updates
			}
		}
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
		
	}	
	post("Getting results and Stopping Grid"){
		always{
			archiveArtifacts artifacts: 'output/**'
			bat "docker-compose down" //stopping server
		}	
	}
}