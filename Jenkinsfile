pipeline {
  agent any
  stages {
    stage('compilar') {
      steps {
        withMaven(maven: 'Maven-1') {
          bat 'mvn clean install -DskipTests=true'
        }
      }
    }
    stage('desplegar') {
      steps {
          deploy adapters: [tomcat7(credentialsId: '6253d53e-5e7d-4ecc-80c5-3295133d0681', path: '', url: 'http://localhost:8081')], contextPath: 'JenkinsJSF2', war: '**/*.war'
      }
    }    
  }
}
