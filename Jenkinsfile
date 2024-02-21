pipeline{
    agent any
    stages{
        stage('checkout the cod'){
            steps{
                 git url: 'https://github.com/Shreyas0901/star-agile-banking-finance/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Push Image'){
            script{
                withCredentials([string(credentialsId: 'shreyas8191', variable: 'Shreyas8191')]) {
                    sh'docker login -u image -p ${dockerhubpwd}'    
                }
                sh'docker push shreyas8191/app'
    }
}
