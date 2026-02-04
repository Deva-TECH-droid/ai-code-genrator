pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel-token')
    }

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
               echo 'Skipping tests for now - no test found...'
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                bat 'npm install -g vercel'
                bat 'vercel --prod --token=%VERCEL_TOKEN% --yes'
            }
        }
    }
}
