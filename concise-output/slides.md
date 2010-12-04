!SLIDE subsection

# Concise Output


!SLIDE commandline incremental

    $ mvn clean compile
    [INFO] Scanning for projects...
    [INFO] ------------------------------------------------------------------------
    [INFO] Building Spring Integration Core
    [INFO]    task-segment: [clean, compile]
    [INFO] ------------------------------------------------------------------------
    [INFO] [clean:clean {execution: default-clean}]
    [INFO] Deleting directory /Users/cbeams/Work/pax/spring-integration/spring-integration-core/target
    [INFO] [resources:resources {execution: default-resources}]
    [INFO] Using 'UTF8' encoding to copy filtered resources.
    [INFO] Copying 0 resource
    [INFO] Copying 6 resources
    [INFO] [compiler:compile {execution: default-compile}]
    [INFO] Compiling 297 source files to /Users/cbeams/Work/pax/spring-integration/spring-integration-core/target/classes
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESSFUL
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 6 seconds
    [INFO] Finished at: Wed Nov 24 15:42:19 MST 2010
    [INFO] Final Memory: 21M/81M
    [INFO] ------------------------------------------------------------------------


!SLIDE commandline incremental

    $ gradle clean compileJava
    :spring-integration-core:clean
    :spring-integration-core:compileJava

    BUILD SUCCESSFUL

    Total time: 5.621 secs


!SLIDE commandline

    $ mvn clean compile
    [INFO] Scanning for projects...
    [INFO] ------------------------------------------------------------------------
    [INFO] Building Spring Integration Core
    [INFO]    task-segment: [clean, compile]
    [INFO] ------------------------------------------------------------------------
    [INFO] [clean:clean {execution: default-clean}]
    [INFO] Deleting directory /Users/cbeams/Work/pax/spring-integration/spring-integration-core/target
    [INFO] [resources:resources {execution: default-resources}]
    [INFO] Using 'UTF8' encoding to copy filtered resources.
    [INFO] Copying 0 resource
    [INFO] Copying 6 resources
    [INFO] [compiler:compile {execution: default-compile}]
    [INFO] Compiling 297 source files to /Users/cbeams/Work/pax/spring-integration/spring-integration-core/target/classes
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESSFUL
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 6 seconds
    [INFO] Finished at: Wed Nov 24 15:42:19 MST 2010
    [INFO] Final Memory: 21M/81M
    [INFO] ------------------------------------------------------------------------


!SLIDE commandline

    $ gradle clean compileJava
    :spring-integration-core:clean
    :spring-integration-core:compileJava

    BUILD SUCCESSFUL

    Total time: 5.621 secs


!SLIDE center

# Broken Windows

![broken windows](broken_windows.jpeg)

!SLIDE incremental bullets

# Broken Windows

* To be fixed...
* ... they must first be *seen*

!SLIDE commandline

    $ mvn clean compile
    [INFO] Scanning for projects...
    [INFO] ------------------------------------------------------------------------
    [INFO] Building Spring Integration FTP Support
    [INFO]    task-segment: [clean, compile]
    [INFO] ------------------------------------------------------------------------
    [INFO] [clean:clean {execution: default-clean}]
    [INFO] Deleting directory /Users/cbeams/Work/pax/spring-integration/spring-integration-ftp/target
    [INFO] [resources:resources {execution: default-resources}]
    [INFO] Using 'UTF8' encoding to copy filtered resources.
    [INFO] Copying 0 resource
    [INFO] Copying 3 resources
    [INFO] [compiler:compile {execution: default-compile}]
    [INFO] Compiling 10 source files to /Users/cbeams/Work/pax/spring-integration/spring-integration-ftp/target/classes
    [WARNING] /Users/cbeams/Work/pax/spring-integration/spring-integration-ftp/src/main/java/org/springframework/integration/ftp/session/FtpSession.java:[63,18] ls(java.lang.String) in org.springframework.integration.ftp.session.FtpSession implements <F>ls(java.lang.String) in org.springframework.integration.file.remote.session.Session; return type requires unchecked conversion
    found   : org.apache.commons.net.ftp.FTPFile[]
    required: F[]

    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESSFUL
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 5 seconds
    [INFO] Finished at: Wed Nov 24 17:10:18 MST 2010
    [INFO] Final Memory: 21M/81M
    [INFO] ------------------------------------------------------------------------

!SLIDE commandline

    $ gradle clean compileJava
    :spring-integration-ftp:compileJava
    /Users/cbeams/Work/pax/spring-integration/spring-integration-ftp/src/main/java/org/springframework/integration/ftp/session/FtpSession.java:63: warning: ls(java.lang.String) in org.springframework.integration.ftp.session.FtpSession implements <F>ls(java.lang.String) in org.springframework.integration.file.remote.session.Session; return type requires unchecked conversion
    found   : org.apache.commons.net.ftp.FTPFile[]
    required: F[]
            public FTPFile[] ls(String path) {
                             ^
    1 warning

    BUILD SUCCESSFUL

    Total time: 4.874 secs


!SLIDE incremental bullets commandline

    $ mvn clean compile | wc
         351    1626   22858


    $ gradle clean compileJava | wc
         113     257    6378


!SLIDE incremental bullets commandline

    $ mvn clean test | wc
         550432 2046401 74486400


    $ gradle clean test | wc
         22748   84781 3057486

!SLIDE incremental bullets

# 25x less output
* not bad
* but 22,748 lines is still *way* too much

!SLIDE code small

    @@@ Groovy
    test {
        logging.captureStandardOutput(LogLevel.INFO)
    }


!SLIDE incremental bullets commandline

    $ mvn clean test | wc
         550432 2046401 74486400


    $ gradle clean test | wc
         227     317    8792

!SLIDE incremental bullets

# 8,472x less output
* that's better
