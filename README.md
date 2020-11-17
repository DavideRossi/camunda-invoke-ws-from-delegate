# Calling a SOAP WS from a Camunda delegate

Forked from https://github.com/camunda/camunda-get-started-java.

The Camunda/Get Started/Java Process Application modified so that the delegate for the Process Request service task now calls an external SOAP Web Service by using a development-time generated proxy.
The code for the proxy and related artifacts is created by running the `wsimport` goal of the `jaxws` Maven plugin, which is part of the `package` lifecyle phase (translation: it is executed automatically when you create the WAR file running `mvn package` or you can run it directly with `mvn jaxws:wsimport`).

An `Examine process variables` user task has been added to give the chance to take a peek at the process variables (specifically `greet` should contain `"Hello <customerId>"`).

The example has been designed to interact with [this](https://github.com/DavideRossi/HelloJEEWS) Web Service JEE application and assumes that the service endpoint is http://172.17.0.2:8080/jeews-1.0-SNAPSHOT/WS, change the `WS.wsdl` `service` section accordingly if this is not the case (or, even better, replace `WS.wsdl` altogether with the WSDL of your running service).

License: The source files in this repository are made available under the [Apache License Version 2.0](./LICENSE).
