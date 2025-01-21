pipeline
{
    agent any
    environment
    {
        DOTNET_CLI_HOME="${env.WORKSPACE}/.dotnet"
    }
    stages
    {
        stage('Checkout')
        {
            steps
            {
                git 'https://github.com/salman1256/appsecond.git'
                echo 'Checkout completed'
            }
        }
        stage('Restore')
        {
            steps
            {
                bat 'dotnet restore'
                echo 'Restore all packages'
            }
        }
        stage('Build')
        {
            steps
            {
                bat 'dotnet build'
                echo 'Build Completed'
            }
        }

        stage('Run')
        {
            steps
            {
                bat 'dotnet run'
                echo 'Completed Run' 
                
            }
        }
    }
}
post
{
    success
    {
        echo 'Pipeline completed successfully'
    }
    failure
    {
        echo 'Pipeline Failed  again'
    }
}
