pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Joselm11/nodejs-app.git'
            }
        }

        stage('Setup Node.js') {
            steps {
                sh '''
                curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
                . ~/.nvm/nvm.sh
                nvm install 18
                nvm use 18

                node -v
                npm -v
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                . ~/.nvm/nvm.sh
                npm install
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                . ~/.nvm/nvm.sh
                npm run build
                '''
            }
        }
    }
}
