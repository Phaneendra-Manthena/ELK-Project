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
        ansiblePlaybook becomeUser: 'ansibl',
          credentialsId: 'newansible',
          installation: 'Ansible',
          inventory: './hosts',
          playbook: './tree.yml'
          
        ansiblePlaybook becomeUser: 'ansibl',
          credentialsId: 'newansible',
          installation: 'Ansible',
          inventory: './hosts',
          playbook: './playbook.yml'
      }
    }
  }
}
