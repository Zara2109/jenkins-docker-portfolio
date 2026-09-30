pipeline {

    agent any

    stages {

        stage('Build Docker Image') {

            steps {

                sh 'docker build -t zahrah-portfolio .'

            }

        }

        stage('Deploy Website') {

            steps {

                sh '''
                docker rm -f portfolio || true

                docker run -d \
                --name portfolio \
                -p 80:80 \
                zahrah-portfolio
                '''
            }
        }
    }
}