pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Server') {
          agent {
            docker {
              image 'maven:3.5-jdk-8-slim'
            }

          }
          steps {
            sh '''echo "Building Server Code.."
mvn -version
mkdir -p target
touch "target/server.war"'''
            stash(name: 'Server', includes: '*/*.war')
          }
        }
        stage('Client') {
          steps {
            sh '''echo "building client code"
npm install --save react
mkdir -p dist
cat > dist/index.html <<EOF
hello!
EOF
touch "dist/client.js\''''
          }
        }
      }
    }
  }
}