sleep 15

node {

  stage('Checkout') {
    checkout scm
  }
  
  stage('Build') {
    isUnix() ? sh('ls -l') : bat('dir')
    sleep 15
  }
  
  stage('Static Analysis') {
    sleep 5
  }
  
  stage('Unit Tests') {
    sleep 5
  }
  
  stage('Functional Tests') {
    sleep 5
  }
    
  stage('Deployment') {
    sleep 5
  }
  
  stage('System Tests') {
    sleep 5
  }
}

