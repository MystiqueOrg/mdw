  

sleep 15

node {
  step([$class: 'GitHubSetCommitStatusBuilder', statusMessage: [content: 'Does this do anything?']])
  sleep 5
  stage('Checkout') {
    step([$class: 'GitHubSetCommitStatusBuilder', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'checkout']])
    checkout scm
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

