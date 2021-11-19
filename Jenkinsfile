node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/hazelnutlove/synk123.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: 'f65ad61c-06f2-4536-8f24-6053572ff733', snykInstallation: 'SnykSec', snykTokenId: 'snykKey'
       
   }

}
