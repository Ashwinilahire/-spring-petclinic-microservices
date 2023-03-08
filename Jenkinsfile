pipeline {
  agent {
  
  docker { image 'openjdk:17' }
  }
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
        echo 'Building imgaes.......'
         sh 'mvn clean install'
         sh 'java -jar jar-location.jar'
         sh './mvnw clean install -P buildDocker'
      }
    }

   stage ('Start') {
      steps {        
        echo 'Docker compose up ....'
        sh 'docker-compose up'
        }
       }

      }
}
