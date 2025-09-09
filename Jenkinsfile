pipeline{
    agent any
    environment {
        PM2_HOME = "C:\\Users\\neeraj\\.pm2"
    }
    tools {nodejs "node"}
    stages {
        stage('Clone Repository'){
            steps{
                git branch: 'master',
                    url: 'https://github.com/neechaudhary/webline-cloud.git'
            }
        }
        
        stage('Install Dependencies'){
            steps {
                bat 'npm install'
            }
        }
         stage('Install pm2'){
            steps {
                bat 'npm install pm2 -g'
            }
        }
        
        stage('Deploy'){
            steps {
                bat 'npx pm2 startOrRestart pm2.config.json'
            }
        }
    }
}
