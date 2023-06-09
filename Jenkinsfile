pipeline {
  agent any

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
       ansiblePlaybook becomeUser: 'jenkins',
                   colorized: true,
                   credentialsId: 'jenkins-slave',
                   installation: 'Ansible',
      inventory: './hosts',
          playbook: './tree.yml'
          
    credentialsId: 'jenkins-slave',
   inventory: './hosts',
      playbook: './playbook.yml'
        sh 'ansible-playbook tree.yml'
        sh 'ansible-playbook playbook.yml'
        sh 'ansible all -m ping'
      }
    }
  }
}
