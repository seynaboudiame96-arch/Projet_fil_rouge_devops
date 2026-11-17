pipeline {
    agent any

    stages {
        stage('1. Checkout Git') {
            steps {
                echo 'Récupération du code source depuis GitHub...'
            }
        }

        stage('2. Build des images Docker') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('3. Déploiement des conteneurs') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('4. Vérification des services') {
            steps {
                sh 'docker compose ps'
            }
        }
    }

    post {
        success {
            echo 'Pipeline CI/CD terminé avec succès !'
        }
        failure {
            echo 'Erreur lors de exécution du pipeline.'
        }
    }
}