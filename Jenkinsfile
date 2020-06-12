node{

   def tomcatWeb = '/opt/apache-tomcat-7.0.104/webapps'
   def tomcatBin = '/opt/apache-tomcat-7.0.104/'
   
   def tomcatStatus = ''
   stage('SCM Checkout'){
        git 'https://github.com/choudharyabhinav15/webapp1.git'
   }
   
   stage('Compile-Package-create-war-file'){
        // Get maven home path
        def mvnHome =  tool name: 'MVN_HOME', type: 'maven'   
        sh "${mvnHome}/bin/mvn install"
    }
    
    stage('Deploy to Tomcat'){
        sh "cp target/oraclesampleapp.war \"${tomcatWeb}/oraclesampleapp.war\""
    }
      stage ('Start Tomcat Server') {
        sleep(time:5,unit:"SECONDS") 
        sh "${tomcatBin}/startup.sh"
   }
}
