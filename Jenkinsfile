#!/usr/bin/env groovy

maven_docker_build_image = 'maven:3.5.4-ibmjava-8-alpine'

node {
	stage('Checkout source code') {
		cleanWs()
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GITCRED', url: 'https://github.com/satyendra216/simple-java-maven-app']]]) 
        }
	stage('Pull latest Terraform Docker image') {
            sh "docker pull ${maven_docker_build_image}"
        }

	stage('Maven Build') {
        	wrap([$class: 'AnsiColorBuildWrapper', 'colorMapName': 'xterm']) {
                    withDockerContainer(image: "${maven_docker_build_image}}", args: "" ) {
    		sh """ 
                       sudo mvn --version
                """
	}
}
}
}


