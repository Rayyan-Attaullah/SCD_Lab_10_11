pipeline {


    agent any
    
    stages {
        stage('Checkout') {

            steps {
                // Checkout code from GitHub repository
                git 'https://github.com/aditya-sridhar/simple-reactjs-app.git'
            }

        }
        
        stage('Dependency Installation') {

            steps {
                // Install dependencies for frontend (assuming npm)
                echo 'Installing dependencies...'
                echo 'npm install'
            }

        }
        
        stage('Build Docker Image') {

            steps {
                // Build Docker image
                echo 'Building Docker image...'
                echo 'docker build -t your-dockerhub-username/your-image-name .'
            }

        }
        
        stage('Run Docker Image') {

            steps {
                // Run Docker image as a container
                echo 'Running Docker image...'
                echo 'docker run -d -p 8080:80 your-dockerhub-username/your-image-name'
            }

        }
        
        stage('Push Docker Image') {

            steps {
                // Push Docker image to Docker Hub
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    echo 'Logging in to Docker Hub...'
                    echo 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                    
                    echo 'Pushing Docker image to Docker Hub...'
                    echo 'docker push your-dockerhub-username/your-image-name'
                }
            }
        }
    }

    
}
