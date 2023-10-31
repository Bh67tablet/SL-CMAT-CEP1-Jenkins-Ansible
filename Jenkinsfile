pipeline{
    agent any
    stages{
        stage('clone the repo')
        {
            steps{
                git branch: 'main', url: 'https://github.com/Sonal0409/SL-CMAT-CEP1-Jenkins-Ansible.git'
            }
        }
        
        stage('run playbook1')
        {
            steps{
                ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'PlaybookInstall.yml'
            }
        }
        
        stage('Run playbook Deployment')
    {
        
        steps{
            ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'PlaybookDeployment.yml'
        }
        
        }
        
    }
}
