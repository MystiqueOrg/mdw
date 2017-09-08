

sleep 15

node {

  stage('Checkout') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'checkout']])
    checkout scm
  }
  
  stage('Build') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'build']])
    isUnix() ? sh('ls -l') : bat('dir')
    sleep 15
  }
  
  stage('Static Analysis') {
    sleep 5
  }
  
  stage('Unit Tests') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'unit test']])
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

