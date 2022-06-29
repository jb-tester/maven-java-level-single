--Possible ways to set:

1. compiler plugin
   1.1.'source' + 'target' - in configuration

```xml

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <configuration>
        <source>1.8</source>
        <target>1.8</target>

    </configuration>
</plugin>
```

1.1.2. in execution  (??)

```xml

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <executions>
        <execution>
            <id>compile-jdk11</id>
            <goals>
                <goal>compile</goal>
            </goals>
            <configuration>
                <source>11</source>
                <target>11</target>
            </configuration>
        </execution>
    </executions>
</plugin>
```

1.2. compiler plugin 'release': for plugin version 3.6+, for jdk 9+
1.2.1. in configuration

```xml

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.8.0</version>
    <configuration>
        <release>8</release>
    </configuration>
</plugin>
```

1.2.2. in execution  (??)

```xml

<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <executions>
        <execution>
            <id>compile-jdk11</id>
            <goals>
                <goal>compile</goal>
            </goals>
            <configuration>
                <release>11</release>
            </configuration>
        </execution>
    </executions>
</plugin>
```

2. properties:
   2.1.

```xml

<properties>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>
</properties>
```   

2.2. for plugin version 3.6+, for jdk 9+:

```xml

<properties>
    <maven.compiler.release>11</maven.compiler.release>
</properties>
```

3. SpringBoot-specific:

```xml

<properties>
    <java.version>17</java.version>
</properties>
```

--Possible values:

1. with/without dot: 8, 1.8: (1.* - only allowed for versions before 9; versions 1.3, 1.4 don't allow different format;
   1.* syntax only works for (1.1) and (2.1) methods)
2. null: result depends on compiler plugin version
3. using property placeholder
4. using unresolved property placeholder
5. some invalid value
6. not set: result depends on compiler plugin version

--Possible locations:

1. current pom
2. inherited from parent pom
3. inherited from parent pom not present locally
4. overriding: different combinations of the settings in parent and current
5. in profiles







