Reproduces the issue with the openapi-generator kotlin-spring generator when interfaceOnly flag is set.

- run generate.sh 
- check that src has no main class
- try running mvn package
- it fails with with the following log lines:

```
[INFO] Scanning for projects...
[INFO] 
[INFO] ------------------< org.openapitools:openapi-spring >-------------------
[INFO] Building openapi-spring 1.0.0
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- resources:3.2.0:resources (default-resources) @ openapi-spring ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Using 'UTF-8' encoding to copy filtered properties files.
[INFO] skip non existing resourceDirectory /Users/ppribula/Work/etc/kotlin-spring-interface-only/src/main/resources
[INFO] skip non existing resourceDirectory /Users/ppribula/Work/etc/kotlin-spring-interface-only/src/main/resources
[INFO] 
[INFO] --- compiler:3.8.1:compile (default-compile) @ openapi-spring ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- kotlin:1.6.21:compile (compile) @ openapi-spring ---
[INFO] Applied plugin: 'spring'
[INFO] 
[INFO] --- resources:3.2.0:testResources (default-testResources) @ openapi-spring ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Using 'UTF-8' encoding to copy filtered properties files.
[INFO] skip non existing resourceDirectory /Users/ppribula/Work/etc/kotlin-spring-interface-only/src/test/resources
[INFO] 
[INFO] --- compiler:3.8.1:testCompile (default-testCompile) @ openapi-spring ---
[INFO] No sources to compile
[INFO] 
[INFO] --- kotlin:1.6.21:test-compile (test-compile) @ openapi-spring ---
[WARNING] No sources found skipping Kotlin compile
[INFO] 
[INFO] --- surefire:2.22.2:test (default-test) @ openapi-spring ---
[WARNING] Parameter 'localRepository' is deprecated core expression; Avoid use of ArtifactRepository type. If you need access to local repository, switch to '${repositorySystemSession}' expression and get LRM from it instead.
[INFO] No tests to run.
[INFO] 
[INFO] --- jar:3.2.2:jar (default-jar) @ openapi-spring ---
[INFO] Building jar: /Users/ppribula/Work/etc/kotlin-spring-interface-only/target/openapi-spring-1.0.0.jar
[INFO] 
[INFO] --- spring-boot:2.6.7:repackage (repackage) @ openapi-spring ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  7.281 s
[INFO] Finished at: 2023-05-12T17:50:06+02:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:2.6.7:repackage (repackage) on project openapi-spring: Execution repackage of goal org.springframework.boot:spring-boot-maven-plugin:2.6.7:repackage failed: Unable to find main class -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginExecutionException
```
