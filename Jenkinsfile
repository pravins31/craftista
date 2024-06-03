pipeline {
  agent none
  stages {
    stage('voting build') {
      agent {
        docker {
          image 'maven:3.8.7-eclipse-temurin-19'
        }

      }
      steps {
        echo 'compling voting app'
        dir(path: 'voting') {
          sh 'mvn compile'
        }

      }
    }

    stage('voting Test') {
      agent {
        docker {
          image 'maven:3.8.7-eclipse-temurin-19'
        }

      }
      steps {
        echo 'Testing voting app'
        dir(path: 'voting') {
          sh 'mvn clean test'
        }

      }
    }

    stage('voting package') {
      agent {
        docker {
          image 'maven:3.8.7-eclipse-temurin-19'
        }

      }
      steps {
        echo 'packaging voting app'
        dir(path: 'voting') {
          sh 'mvn package -DskipTests'
        }

        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven '3.9.7'
  }
}