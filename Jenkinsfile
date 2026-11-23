pipeline {
  agent any
  stages {
    stage('Clonar') {
      steps { checkout scm }
    }
    stage('Validar compose') {
      steps { sh 'docker compose config' }
    }
    stage('Levantar servicios') {
      steps { sh 'docker compose up -d' }
    }
    stage('Verificar') {
      steps { sh 'docker compose ps' }
    }
  }
  post {
    always { sh 'docker compose down' }
  }
}
