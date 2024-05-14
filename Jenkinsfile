agent any
environment{
   DOCKERHUB_CREDENTIALS=credentials('dockerhub695')
}
  stages{
      stage('Build'){
          steps{
              bat 'npm install'

          }
      }
      stage('test'){
          steps{
              bat 'echo "Test is running"'
          }
      }
      stage('Docker build'){
          steps{
              bat 'docker build -t ayesha695/jenkins-integration:latest .'
          }
      }
      stage('login'){
          steps{
              bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
          }
      }
      stage('push'){
          steps{
              bat 'docker push ayesha695/jenkins-integration:latest'
          }
      }
      stage('deploy'){
          steps{
              bat 'echo "Deploying the application"'
          }
      }
    
  }

