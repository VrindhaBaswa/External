pipeline{
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the Docker image..'
                sh 'docker build -t sample:latest .'
            }
        }
        stage('Docker login') {
            steps {
                sh 'docker login -u vrindhabaswa -p 5149@Ashs'
            }
        }
        stage('Push') {
            steps {
                sh 'docker tag sample:latest vrindhabaswa/sample:latest'
                sh 'docker push vrindhabaswa/sample:latest'
            }
        }
    }
    Post {
        Success {
            echo 'Pipeline Successful.'
        }
        Failure {
            echo 'Pipeline Failed.'
        }
    }
}