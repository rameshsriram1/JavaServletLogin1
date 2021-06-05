node{

   def tomcatWeb = 'F:\\ramesh\\Software\\apache-tomcat-9.0.45-windows-x64\\apache-tomcat-9.0.45\\webapps'
   def tomcatBin = 'F:\\ramesh\\Software\\apache-tomcat-9.0.45-windows-x64\\apache-tomcat-9.0.45\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/rameshsriram1/JavaServletLogin1.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      bat "${mvnHome}/bin/mvn package"
      }
/*   stage ('Stop Tomcat Server') {
               bat ''' @ECHO OFF
               wmic process list brief | find /i "tomcat" > NUL
               IF ERRORLEVEL 1 (
                    echo  Stopped
               ) ELSE (
               echo running
                  "${tomcatBin}\\shutdown.bat"
                  sleep(time:10,unit:"SECONDS") 
               )
'''
   }*/
   stage('Deploy to Tomcat'){
     bat "copy target\\JavaServletLogin.war \"${tomcatWeb}\\JavaServletLogin.war\""
   }
      /* stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   } */
}
