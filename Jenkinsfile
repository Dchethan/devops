pipeline {
    agent any
    environment{
        testvariable = "custom_variable_defined"
	}
    stages {
        stage('Build') {
            steps {
                sh 'echo "this is build stage"'
		//sh "echo jenkins home path -> ${BRANCH_NAME}"
		sh "echo this is custom env variables-> ${testvariable}"
            }
        }
        stage('Test') {
	    when{
	    expression {
	     branch 'main'
	    }
	    }
	    steps {
               sh 'echo "this is test stage"'
            }
	}
        stage('Deploy') {
            steps {
               sh 'echo "this is deploy stage"'
            }
        }
    }
    post{
    always{
    sh 'echo "this is POST BLOCK for testing"'
}
}
 }  


