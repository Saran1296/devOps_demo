pipeline{
    agent any
    stages{
        stage('Checkout SCM'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'saran_demo', url: 'https://github.com/Saran1296/devOps_demo.git']])
            }
        }
        stage('Build') {
            steps{
                bat 'mvn package'
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                     bat 'mvn test'  // Run JUnit tests with Maven
                }
            }
        }
        stage('Staging') {
            steps {
                script {
                    echo 'Deploying to staging env...'
                }
            }
        }
        stage('Production') {
            steps {
                script {
                    echo 'Deploying to production env...'
                }
            }
        }
    }
}
