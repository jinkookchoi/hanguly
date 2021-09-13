pipeline {
    agent { docker { image 'ubuntu:18.04' } }
    environment {  
        PROJECT_NAME = 'aiduez-aian_serving'  
        REGISTRY_URL = 'repo.chelsea.kt.co.kr/'
        REGISTRY_CREDENTIALS_ID = 'aiduez_chelsea'
        SONAR_CREDENTIALS_ID = 'aiduez_sonar'
        IMAGE_NAME = 'aiduez/aian_serving'
        BASE_TAG = 'base'
    }  
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World"'
            }
        }
        stage("build and push image"){
            steps{
                script{
                    docker.withRegistry("http://${REGISTRY_URL}", REGISTRY_CREDENTIALS_ID){
                    docker.image("${IMAGE_NAME}:${BASE_TAG}").pull()
                    }
                }
            }
        }
        
    }
}
