pipeline {
    agent any

    stages {
        stage('Build imagen Django') {
            steps {
                sh '''
                    cd biblioteca_virtua
                    docker compose build web
                '''
            }
        }

        stage('Levantar servicios') {
            steps {
                sh '''
                    cd biblioteca_virtua
                    docker compose up -d
                '''
            }
        }

        stage('Migraciones') {
            steps {
                sh '''
                    cd biblioteca_virtua
                    docker compose exec web python manage.py migrate
                '''
            }
        }
    }
}
