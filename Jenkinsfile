pipeline{
  agent {
    docker { image 'ubuntu:latest' }
  }
  stages{
    stage("Wheather"){
      steps{
        sh "curl wttr.in"
      }
    }
  }
}