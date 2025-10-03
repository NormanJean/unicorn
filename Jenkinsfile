pipeline {
    agent any 

    stages {
	    stage('Clone Repository') {
        steps {
            git branch: 'main', url: 'https://github.com/NormanJean/unicorn.git'
        }
		
		stage('Tests') {
			steps {
				sh '''
					source backend/venv/bin/activate
					pytest backend/tests/test_app.py 
				'''
			}
        }
		
        stage('Deploy Application') {
			steps {
				sh 'docker compose up'
			}
        }
	}	

} 