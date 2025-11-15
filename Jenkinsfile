pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('biblioteca_virtua') {
                    sh 'docker compose build'
                }
            }
        }

        stage('Migraciones') {
            steps {
                dir('biblioteca_virtua') {
                    sh 'docker compose run web python manage.py migrate'
                }
            }
        }

        stage('Levantar contenedores') {
            steps {
                dir('biblioteca_virtua') {
                    sh 'docker compose up -d'
                }
            }
        }
    }
}
