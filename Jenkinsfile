node(){
    stage('Cloning Git') {
         git branch: 'master',url: 'https://github.com/Debadutta-Pradhan/HeartiHealthProject.git'
    }
        
    stage('Install dependencies') {
        nodejs('nodejs') {
            powershell 'npm install'
            echo 'Modules installed'
        }
       
    }
    stage('Build') {
        nodejs('nodejs') {
            powershell 'npm run ng -- build --prod'
            echo 'Build completed'
        }
        
    }
   stage('Build images') {
	      steps {
		bat '''
			 
			  docker build -f "Dockerfile" -t lalitha13/hearti-health-app:latest .
			 
		  
		'''
	      }
       }
 stage('Push Docker image') {
	  steps{
		    withDockerRegistry([ credentialsId: "docker_hub", url: "" ]){
			
			bat "docker push lalitha13/hearti-health-app:latest"   
	  	   }
	   }
       } 
      
}
    
