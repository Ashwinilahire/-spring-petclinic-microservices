pipeline {
  agent any
  
  tools {
    jdk 'JAVA_HOME'
    maven 'MAVEN_HOME'
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
         sh 'mvn clean package'
         sh './mvnw clean install -P buildDocker'
      }
    }

   stage ('Start') {
     steps{  
        echo 'Docker compose up ....'
        sh 'COMPOSE_HTTP_TIMEOUT=600 docker-compose up'
        }
       }

      }
}
