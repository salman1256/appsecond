pipeline {
    agent any

    environment {
        DOTNET_CLI_HOME = "${env.WORKSPACE}/.dotnet"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git 'https://github.com/salman1256/appsecond.git'
                echo 'Checkout done' 
            }
        }

        stage('Restore') {
            steps {
                // Restore the NuGet packages
                script {
                    bat 'dotnet restore'
                    echo 'Restore Done'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the application
                script {
                    bat 'dotnet build'
                }
            }
        }
        stage ('Test')
        {
            steps{
                script{
                    bat 'dotnet test --no-build --verbosity normal'
                    echo 'Test Done'

                }

            }
        }

        stage('Run') {
            steps {
                
                script {
                    bat 'dotnet run'
                    echo 'Run Completed'
                }
            }
        }
        stage ('Publish')
        {
            steps {
                
                script {
                    bat 'dotnet publish --configuration Release --output ./publish'
                    echo 'Published Done'
                }
            }
        }


        
    }
    post
    {
        success
        {
            echo 'Pipleline Success'
        }
        failure
        {
            echo 'Failure'
        }
    }


}

