ipeline {
    agent { label 'slave4' }
    stages {
        stage('checkout') {
            steps {
           sh 'rm -rf hello-world-war'
           sh 'git clone https://github.com/parulokesh/hello-world-war/'
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
                sh 'ssh root@172.31.14.255'
                sh ' scp /home/slave4/workspace/Parcelservice_feature-2/target/* root@172.31.14.255:/opt/apache-tomcat-8.5.98/webapps/'
    }
}
    }
}
