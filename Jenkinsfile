pipeline {
    agent any

    stages {
        
        stage('Run Ansible Playbook') {
  steps {
    ansiblePlaybook becomeUser: 'jenkins',
                   colorized: true,
                   credentialsId: 'jenkins-slave',
                   installation: 'Ansible',
                   inventory: './hosts',
                   playbook: './playbook.yml'
  }
}
    }
}
