pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                sh "/opt/apache-maven-3.6.3/bin/mvn clean"
            }
        }
        stage('--test--') {
            steps {
                sh "/opt/apache-maven-3.6.3/bin/mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "/opt/apache-maven-3.6.3/bin/mvn package"
            }
        }
        stage('Email Notification') {
            steps{
              mail bcc: '', body: 'Hi team, welcome to jenkins job alerts......', cc: '', from: '', replyTo: '', subject: 'Jenkins job', to: 'agyr12345678@gmail.com'
            }  
        }
        stage('Send email') {
            steps{
                emailext (to: 'agyr12345678@gmail.com@gmail.com', replyTo: '@gmail.com', subject: "Email Report from - '${env.JOB_NAME}' ", body: readFile("test-output/Extent.html"), mimeType: 'text/html')
            }
        }
    }
}
