pipeline {
    agent any
		environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }
    stages {
        stage('build') {
            steps {
                bat 'git --version'
								bat '''
									echo "Multiline Shell Steps Works too"
									echo "otra linea"
								'''
								bat 'java -version'
								bat 'showJavaVersion.bat'
            }
        }
				stage('Example') {
            steps { 
                bat 'echo Hello World'
								input "Does the envieroment looks ok?"
            }
        }
				stage('Any Name') {
            steps { 
                bat 'echo "Puede tener cualquier nombre"'
            }
        }
    }
		post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}


