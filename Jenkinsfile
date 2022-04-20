pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compile maven app'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'test maven app'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'package maven app'
        echo 'adding new line'
        sh 'mvn package -DskipTests'
        archiveArtifacts '*/*.war'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}
