pipeline {
    agent any
    stages {
        // Checking if pipeline works
        stage('BEGIN') {
            steps {
                sh 'echo "PIPELINE BEGINS"'
            }
        }

        // Try and clone the repo
        stage('Cloning Git') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/alexarasu/bloggy.git']]])     
            }
        }

        // Building a docker image
        stage('Building image') {
            steps{
                script {
                dockerImage = docker.build "Bloggy:latest"
                }
            }
        }

        // Listing docker images
        stage('Listing Images'){
            steps{
                script{
                    sh 'docker image ls'
                }
            }
        }
    }
}