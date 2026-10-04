# Copilot Instructions for starter-junit6

## Build, Test, and Lint Commands

### Maven Setup
- **Build:** `mvn clean package` - Compiles code and creates JAR with dependencies
- **Run tests:** `mvn test` - Execute all unit tests using Maven Surefire
- **Run single test:** `mvn test -Dtest=AppTest` - Run a specific test class
- **Compile only:** `mvn clean compile` - Compile source without tests

### Test Framework
- **Framework:** JUnit 6 (Jupiter) with parameterized test support available
- **Test location:** `src/test/java/com/vorozco/`
- **Test discovery:** Tests use `@Test` annotation; organized by test class per production class

### Dependencies
- JUnit Jupiter API (test scope)
- JUnit Jupiter Params for parameterized tests (optional, already included)
- Maven Assembly plugin for creating fat JAR (main class: `com.vorozco.App`)

## High-Level Architecture

### Project Structure
```
src/main/java/com/vorozco/    - Production code
src/test/java/com/vorozco/    - Test code (one-to-one mapping with main)
pom.xml                         - Maven configuration
target/                         - Compiled output (regenerated)
```

### Build Configuration
- **Java Version:** Release 25 (with source/target compatibility)
- **Encoding:** UTF-8
- **Build Tool:** Maven 3.9.9+ (uses Maven Surefire for test execution)
- **Package Type:** JAR with dependencies included via maven-assembly-plugin

### Typical Workflow
1. Write production code in `src/main/java/com/vorozco/`
2. Write corresponding JUnit 6 tests in `src/test/java/com/vorozco/`
3. Run `mvn test` to verify
4. Run `mvn clean package` to create deployable JAR

## Key Conventions

### Package and Class Naming
- Package: `com.vorozco.*`
- Naming convention: Each production class has a corresponding test class suffixed with `Test` (e.g., `App` → `AppTest`)

### Test Writing
- Use `import org.junit.jupiter.api.Test` for test methods
- Use static imports from `org.junit.jupiter.api.Assertions` (e.g., `assertTrue`, `assertEquals`)
- Test method naming: descriptive method names with `@Test` annotation (not required to prefix with "test")

### Maven Execution Notes
- Java 25 may emit warnings about restricted methods (normal, can suppress with `--enable-native-access=ALL-UNNAMED`)
- Tests are automatically discovered and run by Maven Surefire using JUnit Platform provider
- Assembly plugin creates fat JAR in `target/` with main class entry point in manifest

### IDE Integration
- Project uses standard Maven structure compatible with Eclipse, IntelliJ, VS Code with Java extensions
- `.classpath`, `.project`, `.settings/` are Eclipse-specific; use `mvn eclipse:eclipse` to regenerate if needed
