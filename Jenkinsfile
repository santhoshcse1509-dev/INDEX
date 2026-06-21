pipeline {
agent any

```
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

    stage('Install Vercel CLI') {
        steps {
            sh 'npm install -g vercel'
        }
    }

    stage('Deploy to Vercel') {
        steps {
            withCredentials([
                string(credentialsId: 'vercel-token', variable: 'vcp_8fWSRXhBUpU0fcZO1CTYmzGqyEkLKiNtxWDWdSHNNi06m4G4i91BB8Qh')
            ]) {
                sh '''
                vercel --token=$VERCEL_TOKEN --yes
                '''
            }
        }
    }
}
```

}
