pipeline {
    agent any
    stages {
        stage('BEGIN') {
            steps {
                sh 'echo "PIPELINE BEGINS"'
            }
        }

        stage('Cloning Git') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/alexarasu/bloggy.git']]])     
            }
        }
    }
}