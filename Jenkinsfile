pipeline {

    agent any

    environment { 
        TAG = 'latest'
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "Building..."
                TAG=`date "+%d%m%Y-%H%M%S"`
                docker build -t jluisalvarez/flask_hello:$TAG .
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
           }
        }
        stage('Publish') {
            steps {
                sh '''
                echo "Publishing..."
                echo $TAG
                ''' 
                
           }
        }
        stage('Clean') {
            steps {
                sh '''
                echo "Cleaning..."
                echo $TAG
                ''' 
                
           }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}

