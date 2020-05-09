node {
  
  stage('Checkout Source Code') {
    checkout scm
  }

  stage('Create Docker Image') {
    docker.build("docker_image:5")
  }

pipeline {
  environment {
    registry = "gustavoapolinario/docker-test"
    registryCredential = ‘dockerhub’
  }
  agent any
    
    stage('Building image') {
      steps{
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }

