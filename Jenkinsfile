pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'g++ jenkins_file.cpp -o jenkins'
            }
        }
	stage('Test'){
	    steps{
		sh './jenkins.sh'
	    }
	}
    }
}
