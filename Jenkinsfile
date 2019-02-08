#!/usr/bin/env groovy

node {
	stage('Checkout source code') {
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GITCRED', url: 'https://github.com/satyendra216/simple-java-maven-app']]]) 
        }
	stage('Maven Build') {
  steps {
    sh "mvn --version" // One or more steps need to be included within the steps block.
  }
}
}


