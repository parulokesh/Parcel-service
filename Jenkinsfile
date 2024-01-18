pipeline {
    agent { label 'slave4' }
    stages {
        stage('Checkout') {
            steps {
                sh 'rm -rf Parcel-service'
                sh 'git clone https://github.com/parulokesh/Parcel-service.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
        stage('Run Locally') {
        steps {
                sh 'java -jar target/simple-parcel-service-app-1.0-SNAPSHOT.jar &'
                sleep 30
            }
         }
        stage('Deploy') {
            steps {
                sh 'ssh root@172.31.14.255'
                sh 'scp /home/slave4/workspace/parcelservice1_feature-2/target/simple-parcel-service-app-1.0-SNAPSHOT.jar root@172.31.14.255:/opt/apache-tomcat-8.5.98/webapps'
        }
        }
    } 
}
