pipeline {
  agent any
  stages {
    stage('beats installation') {
      steps {
        sh 'ansible-playbook elastic.beats/elasic.yml'
      }
    }
  }
}