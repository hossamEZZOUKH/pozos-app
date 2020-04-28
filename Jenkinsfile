pipeline {
  
  environment {
    registry = "docker_hub_account/repository_name"
    registryCredential = 'dockerhub'
  }
  agent docker 
  

  stages {  // Define the individual processes, or stages, of your CI pipeline
    stage('Initialize'){
        def dockerHome = tool 'docker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    stage('Checkout') { // Checkout (git clone ...) the projects repository //test git-push
      
      steps {
        checkout scm
        
      }
    }
    stage('Building image') {
      steps{
        script {
          
          docker.build("simple_api:lts","./simple_api")
        }
      }
      }
}
}
