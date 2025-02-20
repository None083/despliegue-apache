pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Copiando los ficheros'
                sh 'npm install'
                sh 'npm run build'                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
		echo 'Desploying...'
		sh 'sudo cp -r ./build/* /var/www/html/'    
	        }
        }
    }
    post {
        success{
            echo 'Pipeline completado con éxito'
        }
        failure{
            echo 'Pipeline fallido'
        }
    }
}
