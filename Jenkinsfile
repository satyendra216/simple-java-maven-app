#!/usr/bin/env groovy

node {
	stage('Checkout source code') {
		cleanWs()
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GITCRED', url: 'https://github.com/satyendra216/simple-java-maven-app']]]) 
        }
	stage('Maven Build') {
    		sh """ 
			cd /var/lib/jenkins
                        mvn --version
                """
	}
}


