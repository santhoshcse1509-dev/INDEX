pipeline {
    agent any

    tools {
        nodejs 'NodeJS-22'
    }

    stages {

        stage('Check Versions') {
            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }

        stage('Check Vercel') {
            steps {
                sh 'npx vercel --version'
            }
        }

        stage('Deploy to Vercel') {
            steps {
                withCredentials([
                    string(credentialsId: 'vercel-token', variable: 'VERCEL_TOKEN')
                ]) {
                    sh '''
                    npx vercel --token=$VERCEL_TOKEN --yes
                    '''
                }
            }
        }
    }
}
