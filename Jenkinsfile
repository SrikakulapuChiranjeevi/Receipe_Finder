pipeline {
	agent any

	stages{
		stage('Github'){
				steps {
					git branch: 'main', credentialsId: 'jen-git-dind', url: 'https://github.com/SrikakulapuChiranjeevi/Receipe_Finder.git'
				}
			}
		}


}

