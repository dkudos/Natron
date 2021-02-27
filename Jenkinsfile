pipeline {
  agent {
    docker {
      image 'natrongithub/natron-sdk:latest'
    }

  }
  stages {
    stage('Make Build Dir') {
      steps {
        sh '''#!/bin/bash

# Make build dir
mkdir builds'''
      }
    }

    stage('Docker Run Build') {
      steps {
        sh '''#!/bin/bash

# Run Docker Build
docker run -it --rm --mount src="$(pwd)/builds",target=/home/builds_archive,type=bind natrongithub/natron-sdk:latest'''
      }
    }

    stage('All Done Message') {
      steps {
        echo 'All Done!'
      }
    }

  }
}