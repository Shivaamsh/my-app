@Library('javahome-libs') _
pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage("Create Folder"){
            steps{
                sh "mkdir -p ${env.JenkinsFile}"
            }
        }
        stage("Maven Build"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deploy to SonarQube"){
            steps{
                sonarqubeDeploy('shiva','35.188.70.52:9000')
            }
        }
    }
}
