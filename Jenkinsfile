pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                { dockerfile true }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                { dockerfile true }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
