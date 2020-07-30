pipeline {
  agent any
  stages {
    stage('GCP') {
      steps {
        sh "pip list"
        withCredentials([file(credentialsId: 'gcp_service_account', variable: 'gcp_cred_file')]) {
          sh "ansible-playbook gcp_playbook.yml --extra-vars secret_file=${gcp_cred_file}"
        }
      }
    }
  }
}