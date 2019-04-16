pipeline {
    environment {
        http_proxy = 'http://gate.zrh.swissre.com:8080/'
        https_proxy = 'http://gate.zrh.swissre.com:8080/'
        HTTP_PROXY = 'http://gate.zrh.swissre.com:8080/'
        HTTPS_PROXY = 'http://gate.zrh.swissre.com:8080/'
    }
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'export http_proxy = http://gate.zrh.swissre.com:8080/'
                sh 'export https_proxy = 'http://gate.zrh.swissre.com:8080/'
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
