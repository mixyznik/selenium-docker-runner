pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d elgalu zalenium"
            }
        }  
        stage("Rnu Test"){
            steps{
                sh "docker-compose up searchmodule"
            }
        }  
       
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }    
    }
}