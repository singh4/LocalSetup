pipeline {
    agent any
    stages {
        stage('Pull Oracle 12C docker image') {
            steps {
                sh 'docker pull sath89/oracle-12c'
            }
        }
        stage('Run the oracle 12C docker container') {
            steps {
                sh 'docker run -d -p 8080:8080 -p 1521:1521 sath89/oracle-12c'
            }
        }
    }
}
