@Library('Jenkins_Shared_Library')
pipeline{
    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndestroy', description: 'Please select create or destroy')
    }
    stages{
        stage("Clean Workspace"){
            steps{
                cleanWorkSpace()
            }
            
        }
        stage("Checkout git"){
            steps{
                checkoutGit()
            }
        }
        
    }
}