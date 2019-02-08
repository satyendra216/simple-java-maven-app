#!/usr/bin/env groovy

node {
	stage('Checkout source code') {
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GITCRED', url: 'https://github.com/satyendra216/simple-java-maven-app']]]) 
        }
}

