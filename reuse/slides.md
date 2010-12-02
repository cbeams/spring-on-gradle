!SLIDE

# Achieving Reuse

!SLIDE

# S2 shared Gradle sources

### https://github.com/springsource/spring-build-gradle

!SLIDE

# Wiki

### https://github.com/springsource/spring-build-gradle/wiki

!SLIDE incremental bullets

# Managed like any other project

* Github
* Source control
* Wiki
* Issues


!SLIDE incremental bullets

# Coded like any other project

* (or at least that's the goal)


!SLIDE

# Git Submodules

!SLIDE commandline incremental

    $ GITURL=git@github.com:springsource/spring-build-gradle.git

    $ git submodule add $GITURL buildSrc
    Cloning into buildSrc...
    remote: Counting objects: 127, done.
    remote: Compressing objects: 100% (99/99), done.
    remote: Total 127 (delta 41), reused 0 (delta 0)
    Receiving objects: 100% (127/127), 44.93 KiB, done.
    Resolving deltas: 100% (41/41), done.

    $ ls
    build         gradle.properties  settings.gradle
    build.gradle  gradlew            spring-integration-event
    *buildSrc*    gradlew.bat        spring-integration-feed
    docs          readme.txt         spring-integration-file




!SLIDE bullets incremental

# git submodules

* Not perfect
* Issues keeping in sync
* Fragile - superprojects depend on submodule git url (which may change)


!SLIDE commandline incremental

# Ugly

    $ SI_GIT_URL=git@git.springsource.org:…/spring-integration.git
    $ git clone $SI_GIT_URL
    ...

    $ git submodule update --init


!SLIDE commandline incremental

# Better

    $ git clone --recursive git@git.springsource.org:…/spring-integration.git
    ...


!SLIDE commandline incremental

# Still Ugly

    $ # make a change to buildSrc

    $ git submodule update
    ...



