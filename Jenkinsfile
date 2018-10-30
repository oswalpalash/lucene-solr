pipeline {
    agent any
    tools {
        ant 'ant-1.10.5'
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                ant ivy-bootstrap
                ant compile
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                ant test
                '''
            }
        }
     }
     post { 
        always { 
            deleteDir() /* clean up our workspace */
        }
    }
}
