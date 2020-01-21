node{   
  stage('SCM Checkout'){
        checkout scm
   }
	
   stage('Build docker image') {
        app = docker.build(image)
    }
    
    stage('Push Image') {
        sh "docker push $image"
    }
    stage('Run Application') {
		sh "docker run --name web-claim -p $hostport:$containerport --restart always -d $image"
    }
}
