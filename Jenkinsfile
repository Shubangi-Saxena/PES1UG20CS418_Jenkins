pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh 'mvn clean complete'
                echo 'Build successful'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sh 'mvn deploy'
            }
        }
    }
  post {
    failure {
      echo 'Pipeline Failed'
    }
  }
}
