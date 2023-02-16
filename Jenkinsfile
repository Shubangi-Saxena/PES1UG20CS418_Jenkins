pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh 'chmod +x scripts/Linux-Build.sh'
                sh 'scripts/Linux-Build.sh'
                archiveArtifacts artifacts: 'bin/Debug/*'
                echo 'Build successful'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
                sh 'echo "Running..."'
                sh 'chmod +x scripts/Linux-Run.sh'
                sh 'scripts/Linux-Run.sh'
                echo 'Testing successful'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                sh 'chmod +x scripts/Linux-Deploy.sh'
                sh 'scripts/Linux-Deploy.sh''
                echo 'Deployment successful'
            }
        }
    }
  post {
    failure {
      echo 'Pipeline Failed'
    }
  }
}
