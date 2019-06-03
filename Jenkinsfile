pipeline{
  agent {
    dockerfile { 
      filename 'dockerfiles/mycustomizeubuntu'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    
    }
  }
  stages{
    stage("check curl"){
      when {branch 'master'}
        steps{
          sh "curl wttr.in"
        }
    }
    stage('check the weather'){
      steps{
         sh 'curl wttr.in'
      }
    }
  }
} 