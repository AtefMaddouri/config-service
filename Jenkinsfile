node {
  
      // reference to maven
	    // ** NOTE: This 'maven-3.5.2' Maven tool must be configured in the Jenkins Global Configuration.   
	    // def mvnHome = tool 'maven-3.10.0'

    stage 'Clone the project'
    git 'https://github.com/AtefMaddouri/config-service.git'

   stage('Preparation') {
     checkout scm
     sh "git rev-parse --short HEAD > .git/commit-id"    
   }

   stage('jar instalation') {        
       sh "./mvnw clean "
   }

   stage('docker build/push') {        
        // sh  "docker run --name config-service -d -p 8761:8761"
   }

   stage('Run On dev server'){
    // sh "docker stop config-service || true && /usr/local/bin/docker/docker rm config-service || true  "
     sh "docker run --name config-service -d -p 8761:8761 --restart always atef/config-service:1.0 "

   }


}
