pipeline{
    agent any
    stages{
        stage('build'){
        steps{
           sh 'npm install -g npm'
        }
     }
    stage('deploy') {
        steps {
        nodejs(nodeJSInstallationName: 'nodejs') {
        withAWS(credentials: 'aws-credentials') {
           sh 'serverless deploy'
        }
      }
    }
  }
 }
}
