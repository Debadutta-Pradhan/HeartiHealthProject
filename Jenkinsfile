node {
         stage ('Checkout SCM'){
                    git branch: 'master',url: 'https://github.com/Debadutta-Pradhan/HeartiHealthProject.git'
         }
         
         stage('Install node modules'){
                      bat "npm install"
         }
         stage('Build'){
                     bat "npm run ng -- build --prod"
         }
         stage('Deploy'){
                      bat "pm2 restart all"
         }
     }
