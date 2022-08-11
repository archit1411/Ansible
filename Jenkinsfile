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
                sh 'chmod 777 hello.sh'
                sh './hello.sh'
            }
        }
    }
}
