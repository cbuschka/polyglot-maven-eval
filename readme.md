# Evaluation of polyglot maven support

## Motivation
* we use maven as the standard for java projects
* maven delivers proven build infrastructure for years
* but: xml configs of maven are verbose
* and gradle is slow and a memory hog

### Question: Does polyglot maven reduce verbosity of pom configurations while retaining current feature state?

## Results summary (as of 2020-02-09)

### Pro
* yaml pom is less verbose
* setup simple: just place a .mvn/ folder with extensions.xml in project root
* supported by idea without extra plugins
* supported by maven 3.5 (possibly earlier)
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
* or import into idea (select pom.yml or folder)

## Links
* https://www.baeldung.com/maven-polyglot
* https://intellij-support.jetbrains.com/hc/en-us/community/posts/360003463819-IntelliJ-not-reading-pom-yml-in-maven-polyglot-project

## TODOs
* try more complex plugins
* convert existing project
* check syntax for plugin inheritance scopes
* try mixing pom.xml/pom.yml as parent/child

## License
[MIT](./license.txt)
