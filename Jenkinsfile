

sleep 15

node {

  stage('Checkout') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'build'], statusMessage: [content: 'Checking out the code']])
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
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'unit test'], statusMessage: [content: 'running tests']])
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

