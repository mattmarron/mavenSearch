# Maven Search CLI
Groovy CLI for searching Maven

## Usage

Assuming you have groovy installed in `/usr/bin/groovy`:

    $ mavenSearch package.or.ClassName

This will return the first result from search.maven.org where the fully-qualified name contains `package.or.ClassName`.

## Filtering By!

### Group

    $ mavenSearch -g org.springframework Autowired
    org.springframework:spring-beans:2.5

### Artifact

    $ mavenSearch -a spring-tx Transactional
    org.springframework:spring-tx:4.3.7.RELEASE

### Version

    $ mavenSearch -v 4.3.7.RELEASE Transactional
    org.springframework:spring-tx:4.3.7.RELEASE

## Output As!

### Gradle

    $ mavenSearch -o gradle -g org.springframework Autowired
    compile 'org.springframework:spring-beans:2.5'

### Maven

    $ mavenSearch -o mvn -g org.springframework Autowired
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-beans</artifactId>
        <version>2.5</version>
    </dependency>

### And many more!

    $ mavenSearch -h | grep output
    -o,--output <arg>     Output as [id|mvn|json|ivy|buildr|gradle|sbt|grape]

_Raw JSON?!_

## Multiple Results

    $ mavenSearch -n 3 org.springframework Autowired
    org.springframework:spring-beans:2.5
    org.springframework:spring-beans:4.3.7.RELEASE
    org.springframework:spring-beans:4.3.6.RELEASE

    
