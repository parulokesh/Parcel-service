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
                sh 'java -jar "/home/slave4/workspace/parcelservice/target/simple-parcel-service-app-1.0-SNAPSHOT.jar"'
    }
}
    }
}
