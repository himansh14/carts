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
  }
}
