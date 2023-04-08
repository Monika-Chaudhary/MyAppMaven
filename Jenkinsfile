node{
	def M2_HOME=tool 'M2_HOME'
	//def setting='$WORKSPACE/settings.xml'
	stage('SCM Git Clone'){
        	checkout scmGit(branches: [[name: '*/main']], extensions: [cleanBeforeCheckout()], userRemoteConfigs: [[url: 'https://github.com/Monika-Chaudhary/MyAppMaven.git']])
    	}
    	stage('Maven Build'){
		sh 'java -version'
		//if setting.xml of project then use- sh '$M2_HOME/bin/mvn clean install --settings $setting'
	    	sh '$M2_HOME/bin/mvn clean install'
  	}
    	stage('JUnit test cases'){
	    junit '**/surefire-reports/*.xml'
    	}
}
