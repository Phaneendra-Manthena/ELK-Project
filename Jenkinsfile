pipeline {
  agent {
    label 'slave'
  }

  stages {
    stage('Hello') {
      steps {
        sh '''
          ansible --version
          ansible-playbook --version
          ansible-galaxy --version
        '''
      }
    }
    stage('Run Ansible Playbooks') {
      steps {
        ansiblePlaybook becomeUser: 'ansible',
       credentialsId: 'newansible',
           installation: 'Ansible',
      inventory: './hosts',
          playbook: './tree.yml'
          
    credentialsId: 'newansible',
   inventory: './hosts',
      playbook: './playbook.yml'
        sh 'ansible-playbook tree.yml'
        sh 'ansible-playbook playbook.yml'
        sh 'ansible all -m ping'
      }
    }
  }
}
