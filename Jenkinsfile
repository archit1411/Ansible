def PROD_HOST= "4493ad94a21c.mylabserver.com"
pipeline{
    agent any
    stages{
        stage ('Loggin'){
            steps{
               withCredentials([usernamePassword(credentialsId: 'webserverlogin', usernameVariable: 'USERNAME', passwordVariable: 'USERPASS')]){
                script{
                   sh "sshpass -p $USERPASS -v ssh -o StrictHostKeyChecking=no $USERNAME@$PROD_HOST \"echo hello\""
                }
               }
            }
        }
    }
}
