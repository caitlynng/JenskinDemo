pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: "main", url: 'https://github.com/caitlynng/JenskinDemo.git'
            }
        }
       stage('Build') {
          steps {
               // sh 'chmod a+x mvn'
                sh 'mvn clean package -DskipTests=true'
           }

           post {
                always {
                  archiveArtifacts 'target/*.jar'
                }
            }
       }
    }
}
