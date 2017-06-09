#!groovy

/* Declarative pipeline */
pipeline {
  agent {
    node {
      label 'master'
      customWorkspace 'workspace/hetzner'
    }
  }
  options {
    disableConcurrentBuilds()
    buildDiscarder(logRotator(numToKeepStr: '30'))
    timeout(time: 15, unit: 'MINUTES')
  }
  stages {
    stage('Test msg'){
      steps {
        echo "$(git show -s --pretty=%an)"
        echo "${BUILD_NUMBER}"
        echo "${RUN_DISPLAY_URL}"
        echo "${currentBuild.durationString}"
        echo "Pipeline <${RUN_DISPLAY_URL}|${BUILD_NUMBER}> of branch ${JOB_NAME} by $(git show -s --pretty=%an) finished successfully in ${currentBuild.durationString}."
      }
    }
    stage('Check syntax') {
      steps {
        sh 'molecule syntax'
      }
    }
    stage('Provision environment') {
      steps {
        sh 'molecule create'
      }
    }
    stage('Run ansible') {
      steps {
        sh 'molecule converge'
      }
    }
    stage('Run Tests'){
      steps {
        sh 'molecule idempotence'
        sh 'molecule verify'
      }
    }
/*    stage('Accept code'){
      when { branch "PR-*" }
      steps {
        mergeGithubPullRequest {
          mergeComment('merged by Jenkins')
          disallowOwnCode()
          failOnNonMerge()
          deleteOnMerge()
        }
      }
    }*/
  }

  post {
    always {
      sh 'molecule destroy'
    }
    success {
      mattermostSend color: 'good', message: "Pipeline <${RUN_DISPLAY_URL}|${BUILD_NUMBER}> of branch ${JOB_NAME} by ${BUILD_USER_ID} finished successfully in ${currentBuild.durationString}."
    }
    failure {
      mattermostSend color: 'danger', message: "Pipeline <${RUN_DISPLAY_URL}|${BUILD_NUMBER}> of branch ${JOB_NAME} by ${BUILD_USER_ID} failed in ${currentBuild.durationString}."
    }
  }
}
