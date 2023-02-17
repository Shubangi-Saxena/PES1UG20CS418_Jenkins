pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o jenkins_exec jenkins_PES1UG20CS418.cpp'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment successful'
            }
        }
    }

    post {
        
        failure {
            echo 'Pipeline failed.'
        }
    }
}
