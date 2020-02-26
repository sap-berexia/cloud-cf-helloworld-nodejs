@Library('piper-lib-os') _
node() {
    stage('prepare') {
	piperPipelineStageInit script:this
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	piperPipelineStageBuild script:this buildTool : 'mta'
    }
}
