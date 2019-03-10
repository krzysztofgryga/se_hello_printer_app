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
		    sh 'make test_xunit' || true
		    step([$class: 'XUnitBuilder',
			tresholds:[
				[$class: 'SkippedThreshold', failureThreshold: '0'],
				[$class: 'FailedThreshold',  failureThreshold: '1'],
			tool: [[$class: 'JUniType', pattern: 'test_result.xml']]]]
                   }
        }
	stage('Lint'){
		steps{
		   sh 'make lint'
		     }
    }
}
}
