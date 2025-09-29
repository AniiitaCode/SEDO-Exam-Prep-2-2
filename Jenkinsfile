pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}

