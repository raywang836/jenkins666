pipeline {
  agent any
  stages {
    stage('Sever') {
      steps {
        sh '''echo "Building Server Code.."
mvn -version
mkdir -p target
touch "target/server.war"'''
      }
    }
  }
}