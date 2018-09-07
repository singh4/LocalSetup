pipeline {
    agent any
    stages {
        
        stage('docker container cleanup') {
            steps {
                sh 'docker ps -q -f status=exited | xargs --no-run-if-empty docker rm'
                  }
        }
        
        stage('Pull Oracle 12C docker image') {
            steps {
                sh "docker pull sath89/oracle-12c"
            }
        }
        stage('Run the oracle 12C docker container') {
            steps {
                sh "docker run -d -p 8081:8081 -p 1521:1521 sath89/oracle-12c"
            }
        }
        stage('Pull Weblogic docker image') {
            steps {
                sh "docker pull ismaleiva90/weblogic12"
            }
        }
        stage('Run the Weblogic12 docker container') {
            steps {
                sh "docker run -d -p 7001:7001 -p 7002:7002 ismaleiva90/weblogic12:latest"
            }
        }
    }
}
