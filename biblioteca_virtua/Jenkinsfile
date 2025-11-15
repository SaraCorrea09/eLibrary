pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Migraciones') {
            steps {
                sh 'docker compose run web python manage.py migrate'
            }
        }

        stage('Levantar contenedores') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }
}
