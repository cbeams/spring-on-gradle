!SLIDE subsection
# Separate Concerns


!SLIDE bullets incremental

# Build User Roles

* Build Consumer
* Build Operator
* Build Master

!SLIDE bullets incremental

# Build Consumer

* Depends on Maven artifacts
* Downloads distribution zip
* Reads documentation
* Probably never thinks about the build system

!SLIDE bullets incremental

# Build Operator

* Builds from source (compile, test, etc)
* May update dependency metadata
* May add new subprojects
* Needs IDE integration

!SLIDE bullets incremental

# Build Master

* Everything an operator does
* Releases the project
* Maintains the project build
* Configures CI
* Writes custom build logic for special needs


!SLIDE bullets incremental

## Let's design a build with these users in mind

* Start by separating concerns


!SLIDE bullets incremental

# Build Consumer

* Publish poms and jars to maven repos
* Upload docs and dist zips
* Pretty simple


!SLIDE bullets incremental

# Build Operator

* Make checkout/build/IDE-import dead simple
* Optimize common use cases like compile/test/docs
* Separate declarative from imperative in build scripts
* Make the release process as easy as possible
* Document anything that's not obvious

!SLIDE bullets incremental

# Build Master

* Treat imperative build sources like any other project
* Make it editable in the IDE
* Write tests for the build
* Keep common build code DRY


