pipeline{
  environment{
	REGISTRY = credentials('REGISTRY')		
	REGISTRY_HOST = 3.8.8.67
  }
  agent any
  stages{
    stage("Docker registry login"){
      when {branch 'master'}
        steps{
          sh 'docker login ${REGISTRY_HOST}\
		  -u ${REGISTRY_USR} -p ${REGISTRY_PSW}'
        }
    }
  }
} 