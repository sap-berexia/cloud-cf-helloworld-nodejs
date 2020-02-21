@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
    	buildExecute script:this, buildTool: 'maven'
    }

    stage('deploy') {
    	cloudFoundryDeploy script: this
    }
}
