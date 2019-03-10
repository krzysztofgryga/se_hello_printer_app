pipeline {
    agent any
    stages {
        stage('Deps') {
            steps {
	            sh 'make deps'
		  }
	}
	stage('Test'){
	      steps{
		    sh 'make test'
                   }
        }
	stege('Lint'){
		steps{
		   sh 'lint'
		     }
    }
}
}
