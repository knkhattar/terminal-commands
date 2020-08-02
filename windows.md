. current directory  
.. parent directory

# Tomcat installation script

'''
REM  THIS COMMAND IS USED FOR COMMENTING 

 

@ECHO OFF 

SETLOCAL 

 

set "CATALINA_HOME=C:\xyz\apache-tomcat-8.5.55"  

set "APP_HOME=C:\Users\user1\Documents\brj-working\spring-security-hello-world-example" 

 

set "STOP=%CATALINA_HOME%\bin\shutdown.bat" 

set "START=%CATALINA_HOME%\bin\startup.bat" 

 

ECHO About to run mvn clean install... 

call mvn clean install 

 

timeout /t 2 

ECHO About to run tomcat shutdown... 

call %STOP% 

timeout /t 2 

 

ECHO clean webapps folder.... 

del %CATALINA_HOME%\webapps\* /Q 

del %CATALINA_HOME%\webapps\ROOT /Q 

 

ECHO copying war files in webapps.... 

xcopy "%APP_HOME%\target\spring-security-hello-world-example-0.0.1-SNAPSHOT.war" "%CATALINA_HOME%\webapps" /i  

rename "%CATALINA_HOME%\webapps\spring-security-hello-world-example-0.0.1-SNAPSHOT.war" "ROOT.war" 

 

 

ECHO About to run tomcat start... 

call %START% 

timeout /t 2 

 

ENDLOCAL 

'''
