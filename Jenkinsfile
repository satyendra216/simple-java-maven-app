#!/usr/bin/env groovy

maven_docker_build_image = 'maven:3.5.4-ibmjava-8-alpine'

node {
	stage('Checkout source code') {
		cleanWs()
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GITCRED', url: 'https://github.com/satyendra216/simple-java-maven-app']]]) 
        }
	stage('Pull latest Terraform Docker image') {
            sh "sudo docker pull ${maven_docker_build_image}"
        }

	stage('Maven Build') {
    		sh script: """\
                       docker run \
        		--volume=${WORKSPACE}/settings.xml:/root/.m2/settings.xml \
        		--entrypoint="/usr/bin/mvn" \
        		${maven_docker_build_image} \
                        clean test package
                """
	}
}


