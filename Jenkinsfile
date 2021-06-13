node {
  
   stage('jar instalation') {
     sh "./mvn clean install -DskipTests"
   }

//    stage('docker build/push') {        
//         sh  "docker build -t logisitics/backend_partner_prod${commit_id}  -f Dockerfile.prod  ."
//    }

//    stage('Run On dev server'){

//      sh "docker stop backend_partner_prod || true && /usr/local/bin/docker/docker rm backend_partner_prod || true  "
//      sh "docker run -d --name backend_partner_prod --restart always -p 3020:3020 logisitics/backend_partner_prod${commit_id}  "

//    }


}