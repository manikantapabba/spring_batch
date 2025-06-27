## MVN COMMANDS

Normally we follow below steps to run springboot Application:

- Compile the code
- Package it into a JAR/WAR file (mvn package or mvn install)
- Run the packaged file with java -jar target/app.jar

**mvn clean**
- Deletes the target/ directory, which contains all compiled classes, packaged JARs,
  and other build artifacts from previous runs.

**mvn compile**
- Compiles Java source files from src/main/java. Outputs .class files into target/classes.

**mvn test**
- Compiles the main source code (src/main/java).
- Compiles the test source code (src/test/java).
- Runs the tests using the test framework configured (JUnit, TestNG, etc.).
- Reports test results in the console and generates reports under target/surefire-reports.

**mvn package**
- Compiles the main Java source code (src/main/java).
- Compiles the test source code (src/test/java).
- Runs the unit tests.
- Packages the compiled code into a distributable format like a .jar or .war and places it in the target/ directory.

**mvn install**
- Compiles the main Java source code (src/main/java).
- Compiles the test source code (src/test/java).
- Runs the tests (from src/test/java)
- Packages the app into a .jar or .war file depending on your pom.xml.
- Installs that .jar/.war into your local Maven repository (~/.m2/repository).

**mvn spring-boot:run**
(Runs your Spring Boot application directly from source without packaging (needs Spring Boot Maven plugin)).
- Compiles the source code if needed
- Starts the Spring Boot app immediately from the compiled classes and resources without creating a packaged JAR/WAR
- This means no intermediate build artifact is created or run explicitly


## WHY CLEAN IS COMBINED WITH ABOVE COMMANDS, FOR EX: mvn clean install, etc..##

**The diff b/w using clean and not is: above mvn commands will not delete target/ directory and uses it, if we make changes to 
existing file they will be recompiled with no issues, but the problem arises when we delete a class file or rename it,
deleted file will be still in compiled classes and renamed will be along with original file in compiled files which
causes issues, application.properties may not get updated in build files and Stale compiled test classes might still be
used even after you remove or update them.**





