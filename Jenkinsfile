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
         sh './mvnw clean install -P buildDocker'
      }
    }

  stage ('start service') {
      steps {        
        sh 'docker-compose --file /var/lib/jenkins/workspace/spring-petclinic-microservices/docker-compose.yml up -d'
        sh 'sleep 100'
        }
       }
    

      }
}
