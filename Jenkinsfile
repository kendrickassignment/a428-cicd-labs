node {
    stage('Checkout') {
        checkout scm
    }

    stage('Build and Test in Node.js Container') {
        docker.image('node:lts').inside {
            stage('Install Dependencies') {
                sh 'npm install'
            }

            stage('Build') {
                sh 'npm run build'
            }

            stage('Test') {
                sh 'npm test -- --watchAll=false'
            }
        }
    }
}