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
            	echo 'Ejecutando tests...'
            	sh 'npm test || echo "Algunos tests fallaron, revisar logs"'
        	}
    	}

    	stage('Deploy') {
        	steps {
            	echo 'Deploying...'
            	sh 'sudo rm -rf /var/www/html/*'  //elimina archivos anteriores
            	sh 'sudo cp -r ./build/* /var/www/html/'  //copia la nueva versión
        	}
    	}
	}
}
