pipeline {
    agent any
    enviroment{
        testvarible = "custom_varible_defined"
	}
    stages {
        stage('Build') {
            steps {
                sh 'echo "this is build stage"'
		sh "echo jenkines home path -> ${BRANCH_NAME}"
		sh "echo this is custom env varible -> ${testvarible}"
            }
        }

        stage('Test') {
	    when{
	    expression {
	    $BRANCH_NAME == "main"
	    }
	    }
	    steps {
               sh 'echo "this is test stage"'
            }
	
        stage('Deploy') {
            steps {
               sh 'echo "this is deploy stage"'
            }
        }
    
    post{
    always{
    sh 'echo "this is POST BLOCK for testing"'
}
} 
 }  
 }
}


