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
    stage('Run Ansible Playbook') {
  steps {
     ansiblePlaybook becomeUser: 'ansible', 
     credentialsId: 'newansible',
      installation: 'Ansible',
       inventory: './hosts',
        playbook: './tree.yml'
  }
}
  }
}
