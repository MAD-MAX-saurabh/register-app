pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage("Cleanup Workspace"){
            steps{
            cleanws()
            }
        }
        stage("Checkout from SCM"){
            steps{
            git branch: 'main', credentialsId: 'github', url: 'https://github.com/MAD-MAX-saurabh/register-app'
            }
        }
        stage("Build Application"){
            steps{
            sh "mvn clean package"
            }
        }
        stage("Test Application"){
            steps{
            sh "mvn test"
            }
        }
    }
}
