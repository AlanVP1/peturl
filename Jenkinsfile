pipeline{
    agent any
    
    stages{
        
        stage("checkout"){
            steps{
                git branch:'main', url:'https://github.com/AlanVP1/peturl'
            }    
        }
        
        stage ("build"){
            steps{
                sh "./mvnw package"
            }    
        }
        
        stage("capture"){
            steps{
                archiveArtifacts '**/target/*.jar'
                jacoco()
                junit '**/target/surefire-reports/TEST*.xml'
            }    
        }
    } 
}
