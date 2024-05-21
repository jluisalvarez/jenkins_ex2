pipeline {

    agent any

    parameters {
        string(name: "TAG", defaultValue: "latest", trim: true)
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "Building..."
                params.TAG=`date "+%d%m%Y-%H%M%S"`
                docker build -t jluisalvarez/flask_hello:$params.TAG .
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
                echo $params.TAG
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

