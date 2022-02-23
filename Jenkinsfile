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
                sh 'cp -R gateway-api/build/libs/* docker-setup/shop/gateway-api && cd docker-setup/shop/gateway-api && docker build --tag=gateway-api .'
                sh '''docker tag gateway-api devcvs-srv01:5000/shop2-backend/gateway-api:2-staging && docker push devcvs-srv01:5000/shop2-backend/gateway-api:2-staging'''

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
