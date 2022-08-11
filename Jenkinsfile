def PROD_IP=4493ad94a23c.mylabserver.com

pipeline{
    agent any
    stages{
        stage ('Checking out from git'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/archit1411/Ansible.git']]])
            }
        }
        stage ('2') {
            steps{
                withCredentials([usernamePassword(credentialsId: 'webserverlogin', usernameVariable: 'USER', passwordVariable: 'PWD')]){
                    sh "sshpass -p $PWD -v ssh -o StrictHostKeyChecking=no $USER@$PROD_IP \"echo LoggedIN\""
            }
        }
    }
}
