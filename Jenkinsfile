@Library('Jenkins_Shared_Library') _
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
                checkoutGit('https://github.com/eswari625/Youtube-clone-app.git', 'main')
            }
        }
        
    }
}