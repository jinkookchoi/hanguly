pipeline {
    environment {  
        registry = "jupyter/tensorflow-notebook"
        registryCredential = 'dockerhub'
        dockerImage = ''
    }  
    agent any
    tools {nodejs "node" }
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
            }
        }
        stage('Building image') {
          steps{
            script {
              dockerImage = docker.build registry + ":$BUILD_NUMBER"
            }
          }
        }
        stage("Deploy Image"){
            steps{
                sh 'echo "Hello World ${registryCredential}"'
            }
        }
    }
}
