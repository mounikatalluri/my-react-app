@Library('QT-jenkins-shared-libraries') _
pipeline {
  agent any
  //tools { nodejs 'node14'}
  stages{
    stage('Load Json Config'){
    steps{
      deleteDir()
      checkout scm
      script {
        echo "Loading json config: ${env.WORKSPACE}/pipelineConfig.json"
        configObject = readJSON file: "${env.WORKSPACE/pipelineConfig.json}"
        LoadJsonConfig()
      }
    }
    }
    stage('Build NPM'){
      when {
        anyOf {
          environment name: 'operation', value: 'build';
        }
        steps{
          buildNpm(configObject)
        }
      }
    }
  }
}
