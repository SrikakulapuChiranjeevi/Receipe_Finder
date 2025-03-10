pipeline {
	agent any
	tools {
		nodejs 'NodeJS'

	}
	environment {
		SONAR_PROJECT_KEY = 'Receipe_Finder'

		SONAR_SCANNER_HOME = tool 'sonarqubeScanner'
	}
	stages{
		stage('Github'){
				steps {
					git branch: 'main', credentialsId: 'jen-git-dind', url: 'https://github.com/SrikakulapuChiranjeevi/Receipe_Finder.git'
				}
			}
		stage('Unit Test'){
			steps {
				sh 'npm run'
				sh 'npm install'
			}
		}
		 stage('SonarQube Analysis'){
                        steps {
                                withCredentials([string(credentialsId: 'Receipe_Finder-token', variable: 'SONAR_TOKEN')]) {
				withSonarQubeEnv('sonarqube') {
					sh"""
					{SONAR_SCANNER_HOME}/bin/sonar-scanner \

					-Dsonar.projectKey={SONAR_PROJECT_KEY} \

					-Dsonar.sources=. \

					-Dsonar.host.url=http://3.111.17.135:9000 \

					-Dsonar.login={SONAR_TOKEN)
					"""	
				}
			}
                                
                   }
             }
	}


}

