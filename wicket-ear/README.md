wicket-ear: Wicket Framework used in a WAR inside an EAR.
=========================================================

Author: Ondrej Zizka <ozizka@redhat.com>

What is it?
-----------

This is an example of how to use Wicket Framework 1.5 with JBoss AS, leveraging features of Java EE 6, using the Wicket-Stuff Java EE integration.

Features used:

 * Injection of `@PersistenceContext`
 * Injection of a value from `web.xml` using `@Resource`
 * Injection of a stateless session bean using `@EJB`

This is an EAR version, with the following structure:

* `wicket-ear` - parent module.
** `ejb`: Contains EJB beans and JPA entities. Creates a `.jar` file.
** `war`: Contains the Wicket web application, which uses the EJB beans. Creates a `.war` file.
** `ear`: Packages the EJB JAR and WAR into an EAR. Creates an `.ear` file.


System requirements
-------------------

All you need to build this project is Java 6.0 (Java SDK 1.6) or better, Maven 3.0 or better.

The application this project produces is designed to be run on JBoss Enterprise Application Platform 6 or JBoss AS 7. 

 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](../README.html/#mavenconfiguration) before testing the quickstarts.


Start the JBoss Server
----------------------

 *  Follow the instructions here to [Start the JBoss Server with the _web_ profile](../README.html#startserverweb)


Build and Deploy the Quickstart
-------------------------------

1. Make sure your server is running.
2. Open a command line and navigate to the root of the kitchensink-ear quickstart directory.
3. Type the following in the command line: 
    For JBoss Enterprise Application Platform 6, Maven user settings NOT configured: 

        mvn clean package jboss-as:deploy -s PATH_TO_QUICKSTARTS/example-settings.xml

    For JBoss AS 7 or JBoss Enterprise Application Platform 6, Maven user settings configured: 

        mvn clean package jboss-as:deploy

4. This will build and deploy `ear/target/jboss-as-kitchensink-ear.ear`.
5. To undeploy the application, run this command:

        mvn jboss-as:undeploy

You can also use Eclipse to start the JBoss Enterprise Application Platform 6 or JBoss AS 7 server and deploy the project. See the <a href="https://docs.jboss.org/author/display/AS71/Getting+Started+Developing+Applications+Guide" title="Getting Started Developing Applications Guide">Getting Started Developing Applications Guide</a> for more information.


Access the application (For quickstarts that have a UI component)
----------------------

Access the running application in a browser at <http://localhost:8080/jboss-as-wicket-ear-web>

 * You will see a page with a table listing user entities. Initially, this table is empty.
 * By clicking a link, you can add more users.



Debug the Application
------------------------------------

If you want to debug the source code or look at the Javadocs of any library in the project, 
run either of the following commands to pull them into your local repository. The IDE should then detect them.

      mvn dependency:sources
      mvn dependency:resolve -Dclassifier=javadoc
