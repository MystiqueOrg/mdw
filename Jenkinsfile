sleep 15

node {
   step([$class: 'GitHubCommitStatusSetter', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'ci/mdw'], statusResultSource: [$class: 'ConditionalStatusResultSource', results: [[$class: 'AnyBuildResult', message: 'Building...', state: 'PENDING']]]])

  checkout scm
  isUnix() ? sh('ls -l') : bat('dir')
  sleep 15
  
   step([$class: 'GitHubCommitStatusSetter', contextSource: [$class: 'ManuallyEnteredCommitContextSource', context: 'ci/mdw'], statusResultSource: [$class: 'ConditionalStatusResultSource', results: [[$class: 'AnyBuildResult', message: 'Successfully built', state: 'SUCCESS']]]])

}

sleep 15
