pipeline{
  agent {
    dockerfile { 
      filename 'dockerfiles/mycustomizedubuntu'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    
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