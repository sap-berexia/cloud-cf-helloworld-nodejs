@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	sh "cd /home/user01/workspace/cloud-cf-helloworld-nodejs"
        sh "mbt build --platform cf --target ./"
    }

    stage('deploy') {
    	cloudFoundryDeploy script: this
    }
}
