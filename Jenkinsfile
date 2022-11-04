pipeline {
    agent any
    stages {
        stage ("Pull") {
            steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                    userRemoteConfigs: [[
                        credentialsId: '0fbf5193-beb6-4355-9f4c-9ae153908350',
                        url: 'https://github.com/louhaichi/angular-achat-CICDproject.git']]])
                }
            }
        }
        stage('Build'){
            steps{
                script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
                }
            }
        }
    }
}