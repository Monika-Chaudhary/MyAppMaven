node{
	def M2_HOME=tool 'M2_HOME'
	//def setting='$WORKSPACE/settings.xml'
    step('SCM Git Clone'){
        checkout scmGit(branches: [[name: '*/main']], extensions: [cleanBeforeCheckout()], userRemoteConfigs: [[url: 'https://github.com/Monika-Chaudhary/MyAppMaven.git']])
    }
	step('Maven Build'){
		//if setting.xml of project then use- sh '$M2_HOME/bin/mvn clean install --settings $setting'
	    sh '$M2_HOME/bin/mvn clean install'
	}
	step('JUnit test cases'){
	    junit '**/test-reports/*.xml'
	}
}
