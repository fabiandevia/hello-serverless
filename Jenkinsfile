pipeline{
    agent any
    stages{
        stage('build'){
        steps{
           git 'https://github.com/fabiandevia/hello-serverless'
           sh 'npm install'
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
