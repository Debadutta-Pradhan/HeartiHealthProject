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
}
    
