pipeline{
  agent {
    docker { 
      image 'ubuntu:latest'
    
    }
  }
  stages{
    stage("Wheather"){
      steps{
        sh "apt-get update && apt-get install curl -y"
        sh "curl wttr.in"
      }
    }
  }
}