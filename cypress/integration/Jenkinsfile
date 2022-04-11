pipeline {
    agent any

    stages {
        stage('Clonar o repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/Kevinspiller/testes-api-cy.git'
            }
        }
        stage('Instalar dependencias') {
            steps {
                sh 'npm install'
            }
        }
        stage('Instanciar Serverest'){
            steps {
                sh 'JENKINS_NODE_COOKIE=dontKillMe nohup npx serverest 2>&1 &'
            }
        }
        stage('Iniciar testes'){
            steps {
                sh 'NO_COLOR=1 npx cypress run'
            }
        }
    }
}