pipeline {
    agent any

    tools {nodejs "Nodejs"}
      

    stages {
        stage('Git checkout') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/maksoft121/mak-Trading-UI.git'
                   }
}
        stage('Install npm prerequisites'){
            steps{
                sh'npm audit fix'
                sh'npm install'
                sh'npm run build'
                sh'cd /var/lib/jenkins/workspace/mak-trading-UI/build'
                sh'pm2 --name Trading-UI start npm -- start'
            }
        }
    }
}
