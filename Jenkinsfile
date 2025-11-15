pipeline {
    agent any

    stages {
        stage('Build imagen Django') {
            steps {
                dir('eLibrary') {         
                    sh 'docker compose build web'
                }
            }
        }

        stage('Levantar servicios') {
            steps {
                dir('eLibrary') {
                    sh 'docker compose up -d'
                }
            }
        }

        stage('Migraciones') {
            steps {
                dir('eLibrary') {
                    sh 'docker compose exec django_app python manage.py migrate'
                }
            }
        }
    }
}
