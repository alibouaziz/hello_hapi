#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }

    stages {
        stage('playing') {
            steps {
                script {
                    parallel "test1":{
                        echo 'test1...'
                    }, "test2":{
                        echo 'test2...'
                    }
                    //parallel(running_set)
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
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
