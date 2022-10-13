pipeline {
    agent  { label '.NET' }
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
    }

}