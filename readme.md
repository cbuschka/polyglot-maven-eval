# Evaluation of polyglot maven support

## Results summary (as of 2020-02-09)

### Pro
* supported by IDEA
* supported by Maven 3.5
* build works out of the box as expected with pom.xml

### Contra
* no suggestions in idea pom.yml
* must deal with strange exceptions when yaml does not match pom model
```text
Caused by: org.yaml.snakeyaml.constructor.ConstructorException: Cannot create property=configuration for JavaBean=Plugin [org.apache.maven.plugins:java-compiler-plugin]
 in 'reader', line 23, column 7:
        - artifactId: java-compiler-plugin
          ^
org.yaml.snakeyaml.nodes.SequenceNode cannot be cast to org.yaml.snakeyaml.nodes.MappingNode
 in 'reader', line 26, column 9:
            - source: 8
            ^
```

## Setup
* treat as standard maven project
* run ```mvn clean install``` on command line
* or import into idea

## Links
* https://www.baeldung.com/maven-polyglot
* https://intellij-support.jetbrains.com/hc/en-us/community/posts/360003463819-IntelliJ-not-reading-pom-yml-in-maven-polyglot-project


## License
[MIT](./license.txt)
