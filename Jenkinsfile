pipeline{
  agent {
    docker { 
      image 'ubuntu:latest'
    
    }
  }
  stages{
    stage("Wheather"){
      steps{
        sh "apt-get update && apt-get install curl"
        sh "curl wttr.in"
      }
    }
  }
}