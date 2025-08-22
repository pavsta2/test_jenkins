pipeline {
    agent any
 
    stages {
        stage('Get code from Git') {
            steps {
                git branch: 'main', url: 'https://github.com/pavsta2/test_jenkins'
            }
        }
        stage('Starts tests') {
            steps {
                sh 'python3 -m pytest . --junit-xml=report.xml'
                junit keepProperties: true, keepTestNames: true, stdioRetention: 'ALL', testResults: 'report.xml'
            }  
        }
    }
}
