pipeline {
   agent any

   stages {
      stage('Checkout') {
         steps {
            git credentialsId: 'git@github.com', url: 'git@github.com:robleney/fleetman-webapp.git'
         }
      }
      stage('Build') {
          steps {
            sh "mvn package"
          }
      }
      stage('Results') {
          steps {
               junit '**/target/surefire-reports/TEST-*.xml'
               archiveArtifacts 'target/*.jar'
          }
      }
   }
}
