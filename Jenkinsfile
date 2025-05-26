pipeline {
    agent any

    environment {
        VENV = ".venv"
    }

    stages {
        stage('Setup') {
            steps {
                sh 'python3 -m venv $VENV'
                sh '. $VENV/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. $VENV/bin/activate && PYTHONPATH=. pytest'	
				    }
        }
    }
}
