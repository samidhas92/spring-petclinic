pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/samidhas92/spring-petclinic'
      }
    }

    stage('Build') {
      steps {
        sh './mvnw clean package'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        sh '''./mvnw sonar:sonar -Dsonar.projectKey=PetClinic -Dsonar.host.url=http://sonarqube:9000 -Dsonar.login=squ_587f0b7c447ff4eb8a1290706eb36450b4c4a804
'''
      }
    }

  }
}