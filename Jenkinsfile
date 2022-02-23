pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                { dockerfile true filename 'Dockerfile'}
            }
            steps {
                sh 'mvn --version'
            }
         stage('Make docker image') {
            steps {
                sh '''docker tag boxfuse 10.129.0.4:8123/boxfuse && docker push 10.129.0.4:8123/boxfuse'''

      }
    }
        }
        stage('Front-end') {
            agent {
                { dockerfile true filename 'Dockerfile2'}
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
