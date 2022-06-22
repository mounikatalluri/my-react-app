  @Library('QT-jenkins-shared-libraries') _
  pipeline {
  agent any
  stages{
    stage('Load Json Config'){
      steps{
        deleteDir()
        checkout scm
        //script {
        //echo "Loading json config: ${env.WORKSPACE}/pipelineConfig.json"
        // configObject = readJSON file: "${env.WORKSPACE/pipelineConfig.json}"
        //LoadJsonConfig()
        //}
      }
    }
    stage('Build NPM'){
      tools {
        nodejs '16.15.1'
      }
      steps{
        buildNpm()
      }
    }
    stage('Deploy to Development Environment'){
      when{
        environment name: 'operation', value: 'deploy-to-Dev'
      }
      steps{
        Deployment(config,Environment)
      }
    stage('Smoke Test'){
      steps{
        seleniumTest(config,Environment)
      }
    }
    }
  }
  }
