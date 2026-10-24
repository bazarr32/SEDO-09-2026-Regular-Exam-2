
pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')
    }

    stages {
        stage('Restore') {
            steps {
                bat 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build Homies.sln --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test Homies.sln --no-build'
            }
        }
    }
}
