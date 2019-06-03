pipeline{
  agent any
  stages{
    stage("My first stage"){
      steps{
        echo "Hola!!"
      }
    }
    stage("Stage myself"){
      steps{
        sh "whoami"
      }
    }
    stage("Wheather"){
      steps{
        sh "curl wttr.in"
      }
    }
  }
}