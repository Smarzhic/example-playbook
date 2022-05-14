pipeline {
  agent { label 'ansible_docker' }
  stages {
    stage('First stage'){
      steps {
        sh 'ansible-galaxy install -r requirements.yml'
        sh 'ansible-playbook site.yml -i inventory/prod.yml'
      }
    }
  }
}
