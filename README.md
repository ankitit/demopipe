pipeline {
    agent any
    
    stages {
        stage ('Compile Stage') {
           
           steps {
               withMaven(maven : 'maven_3_0_5') {
                   sh 'mvn clean complie'
               }
           }
     }

          stage ('Testing Stage') {
           
           steps {
               withMaven(maven : 'maven_3_0_5') {
                   sh 'mvn test'

                }
            }
      }
            stage ('Deployment Stage') {
           
           steps {
               withMaven(maven : 'maven_3_0_5') {
                   sh 'mvn deploy'

                }
            }
      }
