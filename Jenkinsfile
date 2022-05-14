pipeline {
  agent { label 'ansible_docker' }
  stages {
    stage('First stage'){
      steps {
        sh 'ansible-vault decrypt secret --vault-password-file vault_pass'
        //sh 'ansible-galaxy install -r requirements.yml'
        sh 'git clone --single-branch --branch 1.0.1 https://github.com/netology-code/mnt-homeworks-ansible.git'
        sh "ansible-playbook site.yml -i inventory/prod.yml --ssh-common-args='-o StrictHostKeyChecking=no'"
      }
    }
  }
}
