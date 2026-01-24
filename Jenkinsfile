#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            //args '-u root'
            //image 'node:14'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                //sh 'npm install'
                sh 'docker inspect -f . node'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
    }
}
