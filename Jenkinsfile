pipeline {
    agent any 

    stages {
        stage('Setup'){
            steps {
                sh 'npm install'            
            }
        }
        stage('Test') {
            steps {
                sh 'npm run cy:run'
            }
        }
        stage('Deploy'){
            steps{
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'mochawesome-report', reportFiles: 'mochawesome.html', reportName: 'EBAC Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}