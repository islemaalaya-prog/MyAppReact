pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Verifier les fichiers') {
            steps {
                bat 'dir'
                bat 'if not exist Client\\Dockerfile exit /b 1'
                bat 'if not exist Server\\Dockerfile exit /b 1'
                bat 'if not exist docker-compose.yml exit /b 1'
                echo 'Tous les fichiers existent'
            }
        }

        stage('Construire image serveur') {
            steps {
                bat 'docker build -t mern-server ./Server'
            }
        }

        stage('Construire image client') {
            steps {
                bat 'docker build -t mern-client ./Client'
            }
        }

        stage('Fin du pipeline') {
            steps {
                echo 'BUILD OK - Images Docker construites'
            }
        }
    }
}
