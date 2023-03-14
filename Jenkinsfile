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
        sh 'cd /home/$USER'
        sh 'docker-compose up'
        sh 'sleep 100'
        }
       }
    

      }
}
