pipeline {
  agent any
  tools {
    maven 'MAVEN HOME' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: '236c877f-0768-4b9a-a70d-b4775652b4ef', path: '', url: 'http://localhost:8087/')], contextPath: '/pipeline', war: '**/*.war' 
        }
      }
    }
  }
}
