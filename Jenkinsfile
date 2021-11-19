node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/arssathi/https-github.com-cltalam-Snykscriptbasedintegration.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '5e502fe3-30d8-455d-acba-a771362a66a1', snykInstallation: 'synk', snykTokenId: 'synkkey'
       
   }

}
