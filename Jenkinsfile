  

sleep 15

node {
  step([$class: 'GitHubCommitStatusSetter', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'My context 1'], statusResultSource: [$class: 'ConditionalStatusResultSource', results: []]])
  sleep 5
  stage('Checkout') {
    step([$class: 'GitHubCommitStatusSetter', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'My context 2'], statusResultSource: [$class: 'ConditionalStatusResultSource', results: []]])    checkout scm
  }
  step([$class: 'GitHubSetCommitStatusBuilder', statusMessage: [content: 'What about this?']])
  sleep 5
  
  stage('Build') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'build']])
    isUnix() ? sh('ls -l') : bat('dir')
    sleep 1
  }
  
  stage('Static Analysis') {
    sleep 2
  }
  
  stage('Unit Tests') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'unit test']])
    sleep 3
  }
  
  stage('Functional Tests') {
    sleep 4
  }
    
  stage('Deployment') {
    sleep 5
  }
  
  stage('System Tests') {
    sleep 6
  }
}

