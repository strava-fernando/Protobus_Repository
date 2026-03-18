# Proto Definitions Repository

This repository contains Protocol Buffers (`.proto`) definitions for the system. These definitions are used to generate language-specific classes for Java, TypeScript, and Python. Currently, the Java classes can be consumed as a Maven dependency in Spring Boot projects.

---

## Project Structure

```text
proto-repo/
 ├── pom.xml
 └── src/main/proto/
      └── sample.proto
```
src/main/proto/ – contains all .proto files

pom.xml – Maven project configuration, includes Protobuf plugin to generate Java classes

## To use this proto (Java)

1. Add the dependency in your Spring Boot project pom.xml:
```xml
<dependency>
    <groupId>com.yourorg.proto</groupId>
    <artifactId>proto-java</artifactId>
    <version>1.0.0-SNAPSHOT</version>
</dependency>

<repositories>
    <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/strava-fernando/proto-definitions</url>
    </repository>
</repositories>
```

2. Create a GitHub Personal Access Token (PAT) with ```read:packages``` permission
3. Configure your Maven settings.xml (in ```~/.m2/settings.xml```) to include the GitHub repository and your PAT:
```xml
<settings>
    <servers>
        <server>
            <id>github</id>
            <username>your-github-username</username>
            <password>your-pat-token</password>
        </server>
    </servers>
</settings>
```

