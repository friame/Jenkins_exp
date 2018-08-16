#!/usr/bin/groovy

// Jenkins pipeline file

 pipeline {
    agent any

    stage ('Checkout') {
                  checkout scm
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_4') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_4') {
                    sh 'mvn test'
                }
            }
        }

        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_4') {
                    sh 'mvn deploy'
                }
            }
        }
    }
 }
