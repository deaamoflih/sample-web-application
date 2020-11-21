node {
  
  
  stage('SCM') {
checkout([$class: 'GitSCM', branches: [[name: '*/test']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/sample-web-application']]])                }
  stage('Build and Anlyzing') {
      withMaven {
        withSonarQubeEnv('sonarqube') {
        def mvnHome = tool name: 'mvn', type: 'maven' 
         def scannerHome = tool 'sonarqube';
        sh "${mvnHome}/bin/mvn package"
        sh "${mvnHome}/bin/mvn sonar:sonar "
  
                }
                }
  }

    
  }
