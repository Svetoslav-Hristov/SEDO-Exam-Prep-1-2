pipeline{
    agent any
    stages{
        stage("Restore Dependencies"){
            
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            } 
            steps{
                echo "Restoring dependencies"
                bat 'dotnet restore'
            }
            
        }
        stage("Build code"){
            
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            } 
            steps{
                echo "Building code"
                bat 'dotnet build --no-restore'
            }
        }
        stage("Run Tests"){
            
            when {
                anyOf {
                    branch 'feature'
                    branch 'main'
                }
            } 

            steps{
                echo "Running tests"
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
    
}