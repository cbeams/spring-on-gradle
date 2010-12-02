!SLIDE bullets incremental

# Why? #


!SLIDE bullets incremental

# Why? #

## To separate concerns


!SLIDE bullets incremental

# Why? #

## To make concepts explicit


!SLIDE bullets incremental

# Why? #

## To unify dependency metadata


!SLIDE left bullets incremental

# Why? #

## To make the build concise


!SLIDE left bullets incremental

# Why? #

## To make the build easy to use


!SLIDE left bullets incremental

# Why? #

## To make the build fast


!SLIDE bullets incremental

# Why? #

## To facilitate reuse


!SLIDE bullets incremental

# Why? #

## To fully automate the release process


!SLIDE bullets incremental

## (details on all that coming up...)


!SLIDE bullets incremental

## But first...


!SLIDE subsection

# Debate #

!SLIDE 

## (We might as well get it out of the way)

!SLIDE bullets incremental

# Gradle may be nice, but...

* Maven POMs are *critical*
* ∴
* the build must be Maven-based
* ... right?


!SLIDE bullets incremental subsection

# Maybe not


!SLIDE code

# apply plugin: 'maven'


!SLIDE command bullets incremental commandline

# apply plugin: 'maven'

* Poms are:
* Generated from Gradle metadata
* Installed with jars to local .m2 cache
* Uploaded to remote Maven repositor(ies)


!SLIDE code command commandline incremental

# apply plugin: 'maven'

    $ gradle install # poms and jars to local m2 cache

    $ gradle uploadArchives # poms and jars to remote repo


!SLIDE bullets incremental
.notes spring-batch vs. spring-integration poms - preloaded browsers

# Result

* Single source of dependency metadata
* Clean, minimal poms
* Separates the concerns of build instructions vs dependency manifest
* Interoperability with Maven-based builds


!SLIDE subsection

# Debate #

!SLIDE bullets incremental

# Gradle may be nice, but...

* Many Spring users know Maven
* ∴
* the build must be Maven-based
* ... right?


!SLIDE bullets incremental subsection

# Maybe not #


!SLIDE bullets incremental

* Assumes Spring users build from source
* *Relatively* uncommon
* But for those that do...
* What is actually required?


!SLIDE bullets incremental

# Building from source needs to:

* be *simple*
* facilitate IDE import
* install Maven poms to local .m2 cache

!SLIDE bullets incremental smbullets

# What's the status quo?

* [Spring 3 Ant Build](http://blog.springsource.com/2009/03/03/building-spring-3)
* *Six steps* - not easy
* IDE import is complicated
* We can definitely do better

!SLIDE commandline

# Maven makes it easy

    $ git clone $GIT_URL
    # Import poms into m2eclipse / IDEA

    $ mvn install
    ...


!SLIDE commandline

# So does Gradle

    $ git clone $GIT_URL
    $ cd spring-project
    $ ./gradlew eclipse # or 'idea'
    # Import projects into IDE

    $ ./gradlew install
    ...


!SLIDE bullets incremental

# Assertion

* As long as building from source is simple, works with their
IDE and interoperates with Maven...
* ... most users will be happy


!SLIDE bullets incremental

# Ultimately

* build system == *implementation decision*
* must meet basic requirements
* (like Maven interop)
* project lead decides what's best


!SLIDE code

# \</debate>?

!SLIDE

# Hardly.


!SLIDE incremental bullets

# Every organization has different needs

* So the debate differs


!SLIDE incremental smbullets

# Needs at SpringSource

* Common deployment infrastructure and procedures
* Distributed team
* No dedicated CM team or buildmaster
* Many projects
* Many users
* Many Maven repositories
* Special versioning needs
* ...

