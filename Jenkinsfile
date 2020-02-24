@Library('piper-lib-os') _
pipeline {
    agent any
    stages {
        stage('prepare') {
            checkout scm
            setupCommonPipelineEnvironment script:this
        }

        stage('build') {
	    steps {
    	    sh "sudo mbt build --platform cf --target ./"
	    }
        }

        stage('deploy') {
    	    cloudFoundryDeploy script: this
        }
}
