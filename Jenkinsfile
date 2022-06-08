pipeline{
    agent{ label 'JDK11'}
    stages{
        stage('Source Code'){
            steps {
                 url: 'https://github.com/subhendusekhar111/nodejsproject.git'
            }
        }
        stage('Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Archiving the project') {
            steps {
                sh script: 'npm pack'
            }
        }
        stage('Test results') {
            steps {
                sh 'npm test'
            }
        }
        stage('Sonar Analysis') {
            steps {
                sh 'npm run sonar'
            }
        }

    }
}