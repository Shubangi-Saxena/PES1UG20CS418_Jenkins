pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    echo 'Building'
                    sh 'mvn clean complete'
                    echo 'Build successful'
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    echo 'Testing'
                    sh 'mvn test'
                }
            }
        }
        stage('Deploy') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    echo 'Deploying'
                    sh 'mvn deploy'
                }
            }
        }
    }
  post {
    failure {
      echo 'Pipeline Failed'
    }
  }
}
