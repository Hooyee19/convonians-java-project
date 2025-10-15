pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }        
        
        stage('Deploy to Tomcat server') {
            steps {
               deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tompass', path: '', url: 'http://44.203.182.126:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
