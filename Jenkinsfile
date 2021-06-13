node {
  
   stage('Permissions') {
        sh 'chmod 775 *'
   }
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
