pipeline {
    agent { label 'master' }
    tools {
        ant 'ant-1.9.2'
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
                sh 'ant test "-Dtests.class=org.apache.lucene.search*"'
            }
        }
     }
     post { 
        always { 
            deleteDir() /* clean up our workspace */
        }
    }
}
