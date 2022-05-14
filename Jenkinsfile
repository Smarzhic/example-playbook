pipeline {
  agent { label 'ansible_docker' }
  stages {
    stage('First stage'){
      steps {
        sh 'ansible-vault decrypt secret --vault-password-file vault_pass'
        sh 'ansible-galaxy install -r requirements.yml'
        sh "ansible-playbook site.yml -i inventory/prod.yml --ssh-common-args='-o StrictHostKeyChecking=no'"
      }
    }
  }
}
