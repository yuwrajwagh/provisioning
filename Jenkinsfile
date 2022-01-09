pipeline {
    agent any 
    parameters {
        choice(name: 'PROJECT', choices: ['TATA', 'BATA'], description: 'Proide the Project')
        choice(name: 'ENV', choices: ['DEV','QA','PROD','DR'], description: 'Provide the environment')
        string ( name: 'COUNT', description :'provide number of ec2 instances')
    }
    stages {
            stage('Checkout') {
                 steps {
                  git branch: 'main', url: 'https://github.com/yuwrajwagh/provisioning.git'
                }
            }
            stage('Build') {
                 steps {
                    sh 'ansible-playbook create-ec2.yaml -e PROJECT=$PROJECT -e ENV=$ENV -e COUNT=$COUNT'
                 }
               }
    }
}
