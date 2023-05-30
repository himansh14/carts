pipeline {
  agent any
   tools {
    maven 'Maven-3.6.3'
  }
  stages {
    stage('Clone Git Repository') {
        steps {
            git credentialsId: 'github-login', url: 'https://github.com/himansh14/carts.git'
        }
    }
    stage('Build') {
      steps {
        echo 'this is the Build  job'
        sh 'mvn clean compile'
      }
    }

    stage('Test') {
      steps {
        echo 'this is the Test job'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        echo 'this is the Package job'
        sh 'mvn package -DskipTests'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts(artifacts: '**target/*.jar', allowEmptyArchive: true)
      }
    }

  }
 
}
