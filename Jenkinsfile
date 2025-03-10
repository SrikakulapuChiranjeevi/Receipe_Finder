pipeline {
	agent any
	tools {
		nodejs 'NodeJS'

	}
	stages{
		stage('Github'){
				steps {
					git branch: 'main', credentialsId: 'jen-git-dind', url: 'https://github.com/SrikakulapuChiranjeevi/Receipe_Finder.git'
				}
			}
		stage('Unit Test'){
			steps {
				sh 'npm jest'
				sh 'npm install'
			}
		}
	}


}

