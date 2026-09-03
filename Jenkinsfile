pipeline {
    agent any

    tools {
        // Nome que você deu à instalação do NodeJS em
        // Manage Jenkins > Tools > NodeJS
        nodejs 'node-18'
    }

    stages {
        stage('Instalar dependências') {
            steps {
                echo 'Instalando dependências do projeto...'
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Executando build...'
                sh 'npm run build'
            }
        }

        stage('Teste') {
            steps {
                echo 'Executando testes...'
                sh 'npm test'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executado com sucesso!'
        }
        failure {
            echo '❌ Pipeline falhou. Verifique os logs acima.'
        }
        always {
            echo 'Pipeline finalizado (independente do resultado).'
        }
    }
}
