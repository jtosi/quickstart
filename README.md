JBoss AS Quickstarts 
====================

These quickstarts will run in both the JBoss AS or JBoss EAP environments. Check the README.md file in each quickstart folder for more details and specific instructions. 

If you want to run the quickstarts in JBoss EAP, we recommend using the JBoss EAP zip. This version chooses the exact dependencies used in EAP and ensures you test and compile against your runtime environment. 

Prerequisites
-------------

To run these quickstarts with the provided build scripts, you will need the following:

1.   Java 1.6, to run JBoss AS and Maven. You can choose from the following:
    *   OpenJDK
    *   Oracle Java SE
    *   Oracle JRockit

2.   Maven 3.0.0 or newer, to build and deploy the examples
    *   Follow the official Maven installation guide if you don't already have Maven 3 installed. 
    *   If you have Maven installed, you can check the version by running this command in a shell prompt:

        > mvn --version 

3.   The JBoss AS 7 distribution zip or the JBoss EAP 6 distribution zip
    *   For information on how to install and run JBoss, refer to the product documentation.

You can also deploy the quickstarts from Eclipse using JBoss tools. For more information on how to set up Maven and the JBoss tools, refer to the <a href="https://docs.jboss.org/author/display/AS71/Getting+Started+Guide" title="Getting Started Guide">Getting Started Guide</a>.



JBoss AS 7 Quickstart Instructions
-----------------------------------

If you are using the JBoss AS 7 Quickstart distribution, the community artifacts are available in the Maven central repository so no additional configuration is needed.


JBoss EAP 6 Quickstart Instructions
-----------------------------------

If you are using the JBoss EAP 6 distribution, you will need to download and configure the Maven repository.

1.   Download the JBoss EAP 6 Maven repository distribution zip and unzip it into a directory of your choice.

2.   Modify the example-settings.xml file located in the root of your quickstarts folder. Replace all instances of 'path/to/jboss-eap/repo' within '&lt;url&gt;file:///path/to/jboss-eap/repo&lt;/url&gt;' with the fully qualified path to the Maven repository you unzipped in the previous step.

3.   When you run Maven commands, you will need to append '-s _PathToQuickstarts_/example-settings.xml' to the command, for example:

      > mvn jboss-as:deploy -s _PathToQuickstarts_/example-settings.xml

4.   If you do not want to specify the alternate path for your user settings on every Maven command, you can configure your user settings as follows:
    *   If you have an existing ~/.m2/settings.xml file, modify it with the configuration information from the example-settings.xml file.
    *   If there is no ~/.m2/settings.xml file, copy the example-settings.xml file to the ~/.m2 directory and rename it to settings.xml.


Building and Deploying the Quickstarts
--------------------------------------

To build and deploy a quickstart, in most cases you will do the following:

1.   Start the JBoss application server.

2.   In a shell prompt, navigate to the root of the quickstart you want to run.

3.   Type the following: 
     *  For AS 7 and EAP 6 configured with the Maven user settings, type: 

        > mvn package jboss-as:deploy 

     *  For EAP 6 that is not configured with Maven user settings, type: 

        > mvn package jboss-as:deploy -s _PathToQuickstarts_/example-settings.xml

4.   See the README file in the individual quickstart folder for specific information on how to run and access the example.

