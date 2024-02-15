@Library('Jenkins_Shared_Library') _
pipeline{
    agent any
    parameters{
        choice(name: 'action', choices: 'create\ndestroy', description: 'Please select create or destroy')
    }
    tools{
        jdk 'jdk17'
        nodejs 'node16'
    }
    environment{
        sonar_home= tool sonar-scanner
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
        //sonarAnalysis
        stage("Sonarqube Analysis"){
            when{
                expression{
                    params.action == 'create'
                }
            }
            steps{
                sonarqubeAnalysis()
            }
        }
        //QualityGate
        stage("Quality Gate"){
            when{
                expression{
                    params.action == 'create'
                }
            }
            steps{
                qualityGate()
            }
        }

        //npminstall
        stage("Install dependencies"){
            when{
                expression{
                    params.action == 'create'
                }
            }
            steps{
                npmInstall()
            }
           
        }
        
    }
}