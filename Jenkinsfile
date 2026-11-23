pipeline {
  agent any
  stages {
    stage('Clonar') {
      steps { checkout scm }
    }
    stage('Validar compose') {
      steps { bat 'docker compose config' }
    }
    stage('Levantar servicios') {
      steps { bat 'docker compose up -d' }
    }
    stage('Verificar') {
      steps { bat 'docker compose ps' }
    }
  }
}
