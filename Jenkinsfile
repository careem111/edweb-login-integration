 pipeline{
   agent {
     kubernetes {
       yaml '''
         apiVersion: v1
         kind: Pod
         metadata:
           name: mypod
         spec:
           containers:
           - name: build-agent
             image: careem785/jenkins-build-agent:1.0
             command: 
              - cat
             tty: true
             volumeMounts:
             - name: dockersock
               mountPath: /var/run/docker.sock 
         '''
        }
    }
    stages {
      stage('Build') {
    	   steps{
	     container('build-agent'){
	       sh 'date'
        	}
	      }
            }
        } 
  }