pipeline {
  agent any
  environment {
    POSTGRES_PASSWORD = credentials('postgres-password')
  }
  stages {
    stage('Clonar') {
      steps { checkout scm }
    }
    stage('Validar compose') {
      steps { bat 'docker compose config -q' }
    }
    stage('Levantar servicios') {
      steps { bat 'docker compose up -d' }
    }
    stage('Verificar') {
      steps { bat 'docker compose ps' }
    }
  }
}
