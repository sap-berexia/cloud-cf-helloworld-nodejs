@Library('piper-lib-os') _
node() {
    stage('prepare') {
	deleteDir()
        checkout scm
        setupCommonPipelineEnvironment script:this
    }

    stage('build') {
	sh "whoami"
	sh "cd /home/user01/workspace/cloud-cf-helloworld-nodejs"
        sh "sudo mbt build --platform cf --target ./"
    }

    stage('deploy') {
    	cloudFoundryDeploy script: this
    }
}
