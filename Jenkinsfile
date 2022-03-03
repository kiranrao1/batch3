pipeline {
    agent any

    stages {
        stage('scm stage ') {
            steps {
                echo 'hello batch4 champs'
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
         
         stage('artifact build ') {
            steps {
                echo 'bulding with maven tool'
                sh 'mvn clean install'
            }
         }
         
         stage('depoly into tomcat ') {
            steps {
                echo 'deploy into tomcat'
                deploy adapters: [tomcat9(credentialsId: '7efb411c-1488-4302-b3ee-bc0b480cc0ff', path: '', url: 'http://34.207.159.204:8080/')], contextPath: null, war: '**/*.war'
            }
         }
    }
}
