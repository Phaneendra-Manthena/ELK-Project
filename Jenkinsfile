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
    ansiblePlaybook becomeUser: 'jenkins',
                   colorized: true,
                   credentialsId: 'jenkins-slave',
                   installation: 'Ansible',
                   inventory: '/etc/ansible/hosts',
                   playbook: '/home/mpvarma997/playbook.yml'
  }
}
  }
}
