@Library('QT-jenkins-shared-libraries') _
pipeline {
  agent any
  stages{
    stage('Load Json Config'){
    steps{
      deleteDir()
      checkout scm
      script {
        echo "Loading json config: ${env.WORKSPACE}/pipelineConfig.json"
        configObject = readJSON file: "${env.WORKSPACE/pipelineConfig.json}"
        //LoadJsonConfig()
      }
    }
    }
    stage('Build NPM'){
        steps{
          buildNpm(configObject)
        }
      }
    }
  }
