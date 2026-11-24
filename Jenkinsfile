pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Cloner le projet') {
            steps {
                echo 'Projet MyAppReact disponible'
                checkout scm
            }
        }

        stage('Verifier les fichiers') {
            steps {
                sh 'ls -la'
                sh 'test -f Client/Dockerfile'
                sh 'test -f Server/Dockerfile'
                sh 'test -f docker-compose.yml'
            }
        }

        stage('Construire image serveur') {
            steps {
                sh 'docker build -t mern-server ./Server'
            }
        }

        stage('Construire image client') {
            steps {
                sh 'docker build -t mern-client ./Client'
            }
        }

        stage('Fin du pipeline') {
            steps {
                echo 'BUILD OK - Images Docker construites'
            }
        }
    }
}
