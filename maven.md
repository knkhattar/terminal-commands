* Create Sample Project
 	. mvn archetype:generate -DgroupId=com.example  -DartifactId=my-first-webapp -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
  
	  <build>
	    <finalName>my-first-webapp</finalName>
	    <plugins>
				<plugin>
					<groupId>org.eclipse.jetty</groupId>
					<artifactId>jetty-maven-plugin</artifactId>
					<version>9.4.30.v20200611</version>
				</plugin>
			</plugins>
	  </build>
  
 * mvn jetty:run -Djetty.http.port=8080
 * mvn clean install -Denv=dev -DskipTests -Pprofile1 -rf :3rdProjectInMultimoduleProj  // rf - resume from
 # mvn reactor 
 * skip projects in reactor - use command below. pl is for project list - it skips submodule1 and 2
 * mvn -pl "!submodule1,!submodule2" install

# mvn deploy
mvn deploy:deploy-file -Dfile=log4j-api-2.14.1.jar -DpomFile=log4j-api-2.14.3.pom -DgroupId=com.example -DartifactId=log4j-api -Dversion=2.14.1 -Dpackaging=jar -DrepositoryId=documentum 
-Durl=https://pkgs.dev.azure.com/youracc/az-devops-test/_packaging/yourfeed/maven/v1
https://help.talend.com/r/en-US/Cloud/api-tester-examples/creating-maven-feed-in-azure-artifacts
