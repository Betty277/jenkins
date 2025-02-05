pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', 
                    credentialsId: 'github-ssh-key', 
                    url: 'git@github.com:Betty277/jenkins.git'
            }
        }

        stage('Deploy to Linux Server') {
            steps {
                echo 'Deploying website to Linux server...'
                sh 'scp -o StrictHostKeyChecking=no -r * server@10.0.2.15:/var/www/html'
            }
        }
    }
}
