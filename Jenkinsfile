pipeline{
  environment{
	REGISTRY = credentials('REGISTRY')		
	REGISTRY_HOST = '3.8.8.67'
  }
  agent any
  stages{
    stage("Docker registry login"){
        steps{
          sh 'docker login ${REGISTRY_HOST}\
		  -u ${REGISTRY_USR} -p ${REGISTRY_PSW}'
        }
    }
  	stage('Unit test'){
  		agent{
  			docker{
  				image '${REGISTRY_HOST}/rust-base'
  			}
  		}
  		steps{
  			sh 'rustup default nightly-2018-04-04'
  			sh 'cargo test'
  		}
  	}
    stage('Smoke tests'){
      agent{
        dockerfile{
          filename 'dockerfiles/docker-compose.dockerfile'
          args '--net host -v /var/run/docker.sock:/var/run/docker.sock'
        }
      }
      steps {
        sh 'docker-compose up -d'
        sh 'sleep 30'
        sh 'curl --fail -I http://0.0.0.0:8888/health'
      }
      post {
        always {
            sh "docker-compose down"
        }
      }        
    }
  }
} 