node{

   def tomcatWeb = 'D:\\Auto_deployment\\apache-tomcat-9.0.30\\apache-tomcat-9.0.30\\webapps'
   def tomcatBin = 'D:\\Auto_deployment\\apache-tomcat-9.0.30\\apache-tomcat-9.0.30\\bin'
   
   def tomcatStatus = ''
   stage('SCM Checkout'){
        git 'https://github.com/<>.git'
   }
   
   stage('Compile-Package-create-war-file'){
        // Get maven home path
        def mvnHome =  tool name: 'maven-3', type: 'maven'   
        sh "${mvnHome}/bin/mvn package"
    }
    
    stage('Deploy to Tomcat'){
        sh "copy target\\JenkinsWar.war \"${tomcatWeb}\\JenkinsWar.war\""
    }
      stage ('Start Tomcat Server') {
        sleep(time:5,unit:"SECONDS") 
        sh "${tomcatBin}\\startup.sh"
   }
}
