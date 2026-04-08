node {
    stage('Checkout') {
        checkout scm
    }

    stage('Install Node.js') {
        sh '''
            apt-get update
            apt-get install -y nodejs npm
            node --version
            npm --version
        '''
    }

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
