pipeline {
    agent  { label 'node-1' }
    stages {
        stage('git') {
            steps {
                git branch: 'master', 
                url: 'https://github.com/gopivurata/dotnetcore-docs-hello-world.git'
            }

        }
        stage('build') {
            steps {
                sh 'dotnet build'
            }
        }
        stage('publish') {
            steps {
                sh 'dotnet publish'
            }
        }
        stage('archive results') {
            steps {
                archive '/home/ubuntu/dotnetcore-docs-hello-world/bin/Debug/net6.0/publish/'
            }
        }
        stage('downloade zip') {
            steps {
                sh 'sudo apt install zip -y'
            }
        }
        stage('zip') {
            steps {
                sh 'zip -r  dotnetcore-docs-hello-world-1.0.0.zip /home/ubuntu/dotnetcore-docs-hello-world/bin/Debug/net6.0/publish'
            }
        }
    }

}