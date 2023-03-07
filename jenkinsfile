pipeline {
  agent any

  tools {
    maven 'Jenkin-Maven'
  }
  stages {

    stage ('Clone') {
      steps {
        echo 'Cloning code.......'
        git 'https://github.com/Ashwinilahire/-spring-petclinic-microservices.git'
      }
    }

    stage ('Build images') {
      steps {
        echo 'Building imgaes......'
        sh '/var/lib/jenkins/workspace/-spring-petclinic-microservices/mvnw clean install -P buildDocker'
      }
    }

   stage ('Start') {
      steps {        
        echo 'Docker compose up ....'
        sh '/var/lib/jenkins/workspace/-spring-petclinic-microservices/docker-compose up'
        }
       }

      }
}
