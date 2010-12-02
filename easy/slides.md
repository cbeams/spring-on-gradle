!SLIDE subsection
.notes discoverability colorization

# Ease of Use

!SLIDE incremental smbullets
.notes discoverability colorization

# Ease of Use

* Gradle Wrapper
* Partial builds
* Task discoverability
* Support source poms
* `gradle help`
* AMQP test exclusions
* Multi-repository deployment


!SLIDE commandline incremental

# Get running with Gradle

    $ git clone --recursive $GIT_URL
    Cloning into spring-integration...
    remote: Counting objects: 19483, done.
    remote: Compressing objects: 100% (10387/10387), done.
    ...
    $ cd spring-integration && ./gradlew eclipse
    :spring-integration-core:eclipseClasspath
    :spring-integration-core:eclipseJdt
    :spring-integration-core:eclipseProject
    :spring-integration-core:eclipse
    :spring-integration-event:eclipseClasspath
    :spring-integration-event:eclipseJdt
    :spring-integration-event:eclipseProject
    :spring-integration-event:eclipse
    ...

    BUILD SUCCESSFUL


!SLIDE commandline incremental

## Wrapper == self-contained builds

    $ git clone --recursive $GIT_URL
    $ cd spring-integration
    $ ./gradlew build
    Downloading http://dist.codehaus.org/gradle/gradle-0.9-rc-3-bin.zip
    ...................................................................
    ...................................................................
    Unzipping /Users/cbeams/.gradle/wrapper/dists/gradle-0.9-rc-3-bin.zip to /Users/cbeams/.gradle/wrapper/dists
    Set executable permissions for: /Users/cbeams/.gradle/wrapper/dists/gradle-0.9-rc-3/bin/gradle
    > Loading
    ...

    BUILD SUCCESSFUL


