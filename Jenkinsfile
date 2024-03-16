pipeline {
  agent any
  parameters {
    gitParameter branchFilter: 'origin/(main|develop|hotfix|release).*', defaultValue: 'main', name: 'git_branch', type: 'PT_BRANCH'
  }
  stages {
    stage('git') {
      steps {
        git branch: "${params.git_branch}", url: 'git@127.0.0.1:1101studio/server/mybatis-plus-generator-maven-plugin.git'
      }
    }
    stage('deploy') {
      steps {
        sh 'mvn clean deploy'
      }
    }
  }
}