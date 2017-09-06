def setBuildStatus(String message, String state, String context, String sha) {
    step([
        $class: "GitHubCommitStatusSetter",
        reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://github.com/<yourRepoURL>"],
        contextSource: [$class: "ManuallyEnteredCommitContextSource", context: context],
        errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
        commitShaSource: [$class: "ManuallyEnteredShaSource", sha: sha ],
        statusBackrefSource: [$class: "ManuallyEnteredBackrefSource", backref: "${BUILD_URL}flowGraphTable/"],
        statusResultSource: [$class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]] ]
    ]);
}

sleep 15

node {

  stage('Checkout') {
    checkout scm
  }
  
  stage('Build') {
    setBuildStatus("In Progress","PENDING","Build","${gitCommit}")
    isUnix() ? sh('ls -l') : bat('dir')
    setBuildStatus("In Progress","SUCCESS","Build","${gitCommit}")
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

