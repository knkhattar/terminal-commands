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
  
 * mvn jetty:run
 * mvn clean install -Denv=dev -DskipTests -Pprofile1 -rf :3rdProjectInMultimoduleProj  // rf - resume from
 # mvn reactor 
 * skip projects in reactor - use command below. pl is for project list - it skips submodule1 and 2
 * mvn -pl "!submodule1,!submodule2" install
