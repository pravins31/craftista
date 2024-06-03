pipeline {
  agent any
  stages {
    stage('voting build') {
      steps {
        echo 'compling voting app'
        dir(path: 'voting') {
          sh 'mvn compile'
        }

      }
    }

    stage('voting Test') {
      steps {
        echo 'Testing voting app'
        dir(path: 'voting') {
          sh 'mvn clean test'
        }

      }
    }

    stage('voting package') {
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