pipeline {
  agent {
    docker {
        image 'carlossg/maven:3-eclipse-temurin-21'
    }
}

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/karlbunnell/jenkins-test.git'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package'  // Assuming Maven is installed on the agent
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
  }
}
