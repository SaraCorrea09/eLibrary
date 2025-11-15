pipeline {
    agent any

    stages {
        stage('Build imagen Django') {
            steps {
                sh 'docker compose build web'
            }
        }

        stage('Levantar servicios') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Migraciones') {
            steps {
                sh 'docker compose exec django_app python manage.py migrate'
            }
        }
    }
}
