pipeline {
  agent { label 'slave' }
  stages {
    stage('beats installation') {
      steps {
        sh 'ansible-playbook elastic.yml'
      }
    }
  }
}