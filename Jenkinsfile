pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                { dockerfile true filename 'Dockerfile'}
            }
        stage('Make docker image') {
            steps {
                sh 'cd /usr/local/boxfuse-sample-java-war-hello/target && docker build --tag boxfuse .'
                sh '''docker tag boxfuse 10.129.0.4:8123/boxfuse && docker push 10.129.0.4:8123/boxfuse'''

      }
    }
        }
        stage('Deploy') {
            agent {
                { dockerfile true filename 'Dockerfile2'}
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
