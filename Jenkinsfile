pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Joselm11/nodejs-app.git'
            }
        }

        stage('Install Node.js & Dependencies') {
            steps {
                sh '''
                apt-get update
                apt-get install -y curl
                curl -fsSL https://deb.nodesource.com/setup_18.x | bash -
                apt-get install -y nodejs

                node -v
                npm -v

                npm install
                '''
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}
