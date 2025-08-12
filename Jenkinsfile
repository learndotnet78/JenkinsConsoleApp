pipeline {
    agent any // or a specific agent/node if needed

    stages {
        stage('Checkout') {
            options {
                    timeout(time: 30, unit: 'MINUTES') // Applies only to this stage
                }
            steps {
                git 'https://github.com/learndotnet78/JenkinsConsoleApp.git' // Replace with your repository URL
            }
        }

        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release'
            }
        }


        stage('Publish') {
            steps {
                sh 'dotnet publish --configuration Release --output E:\\.jenkins\\release'
            }
        }

    }
}
