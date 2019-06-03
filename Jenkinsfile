pipeline{
  agent {
    docker { 
      image 'ubuntu:latest'
      args '-c apt-get install curl'
    
    }
  }
  stages{
    stage("Wheather"){
      steps{
        sh "curl wttr.in"
      }
    }
  }
}