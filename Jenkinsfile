node {    
      //https://medium.com/swlh/jenkins-pipeline-to-create-docker-image-and-push-to-docker-hub-721919512f2
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
            bat 'npm install' //chd
            app = docker.build("charleshoanduong1111/angular-docker-image")    
       }     
      stage('Test image') {           
            app.inside {            
               // sh 'echo "Tests passed"'  //chd  
               bat 'echo "Tests passed"'        
            }    
        }     
       stage('Push image') {
           docker.withRegistry('https://registry.hub.docker.com', 'git') {            
       	   app.push("${env.BUILD_NUMBER}")            
           app.push("latest")        
 		}    
      }
}
