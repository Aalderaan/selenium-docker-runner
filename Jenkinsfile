pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox" //sh for linux
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module1 search-module2 --no-color" //in jenkins there is no colors while running docker
			}
		}
		stage("Stop Grid"){
			steps{
				bat "docker-compose down" //stopping server
			}
		}	
	}
}