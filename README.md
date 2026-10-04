# starter-junit6

A minimal starter project for Java 25 with JUnit 6 (Jupiter) testing framework.

## Prerequisites

- **Java 25** or later
- **Maven 3.9.9** or later (or use the included Maven wrapper)

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/tuxtor/starter-junit6.git
   cd starter-junit6
   ```

2. **Run tests**
   ```bash
   ./mvnw test
   # or: mvn test
   ```

3. **Build the project**
   ```bash
   ./mvnw clean package
   ```

4. **Run the application**
   ```bash
   java -jar target/starter-junit6-1.0-SNAPSHOT-jar-with-dependencies.jar
   ```

## Project Structure

```
src/
├── main/java/com/vorozco/    → Production code
└── test/java/com/vorozco/    → JUnit 6 tests
pom.xml                        → Maven configuration
```

## Writing Your First Test

Tests use JUnit 6 (Jupiter). See `src/test/java/com/vorozco/AppTest.java`:

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertTrue;

public class MyTest {
    @Test
    public void shouldWork() {
        assertTrue(true);
    }
}
```

Run a single test class:
```bash
./mvnw test -Dtest=MyTest
```

## What's Included

- ✅ JUnit 6 (Jupiter) with parameterized tests support
- ✅ Maven build automation
- ✅ Maven wrapper for reproducible builds
- ✅ GitHub Actions testing on every push/PR
- ✅ Dependabot for dependency updates

## Next Steps

- Read `pom.xml` to manage dependencies
- Add more test classes following the `*Test` naming pattern
- Customize package names in `pom.xml` and source files

## License

This is a starter project. Customize as needed.
