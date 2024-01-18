pipeline {
    agent { label 'slave4' }
    stages {
        stage('checkout') {
            steps {
           sh 'rm -rf Parcel-service'
           sh 'git clone https://github.com/parulokesh/Parcel-service.git'
            }
         }
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
                         }
        }
        stage('deploy') {
            steps {
                sh 'java-jar "/home/slave4/workspace/Parcelservice/target/simple-parcel-service-app-1.0 root@172.31.14.255:/opt/apache-tomcat-8.5.98/webapps/'
    }
}
    }
}
