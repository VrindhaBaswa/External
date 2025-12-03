pipeline{
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the Docker image..'
                sh 'docker build -t mypythonapp:latest .'
            }
        }
        stage('Docker login') {
            steps {
                sh 'docker login -u vrindhabaswa -p vrindha000'
            }
        }
        stage('Push') {
            steps {
                sh 'docker tag mypythonapp:latest vrindhabaswa/sample:latest'
                sh 'docker push vrindhabaswa/sample:latest'
            }
        }
    }
    post{
        success{
            echo 'Pipeline completed successfully.'
        }
        failure{
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}