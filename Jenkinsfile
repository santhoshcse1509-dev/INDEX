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

        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Success') {
            steps {
                echo 'Build completed successfully'
            }
        }
    }
}
