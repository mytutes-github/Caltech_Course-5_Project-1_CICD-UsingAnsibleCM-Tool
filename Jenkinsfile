pipeline{
    agent any
    tools {
      maven 'Apache_Maven_3.6.3'
    }
    environment {
      DOCKER_TAG = getVersion()
    }
   
    stages{
        stage('SCM'){
            steps{
                
                git credentialsId: 'SSH_Git-Jenkins', url: 'git@github.com:mytutes-github/Caltech_Course-5_Project-1_CICD-UsingAnsibleCM-Tool.git'
            }
        }
    }
}

def getVersion(){
    def commitHash = sh label: '', returnStdout: true, script: 'git rev-parse --short HEAD'
    return commitHash
}