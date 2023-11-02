pipeline{
    
    agent any
    stages{
      stage('Clone the repo with playbook')  
      {
          steps{
              git branch: 'main', url: 'https://github.com/Bh67tablet/SL-CMAT-CEP1-Jenkins-Ansible.git'
          }
      }
      stage('install maven & Docker')
      {
          steps{
              ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'PlaybookInstall.yml'
          }
      }
      stage('Execute Ansible deployment playbook')
      {
          steps{
              ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'PlaybookDeployment.yml'
          }
      }
    }
}
