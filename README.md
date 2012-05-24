Airbrake (was Hoptoad) Notifier for Logback
===========================================

A fork of [AMEE / hoptoad-java-notifier](https://github.com/AMEE/hoptoad-java-notifier) which is a fork of Luca Marrocco's [hoptoad notifier](http://code.google.com/p/hoptoad/).

Licensed under the Apache License, Version 2.0.


Code Changes
------------
* Modified to work with [Logback](http://logback.qos.ch/) instead of log4j.


Example Airbrake Appender logback.xml
-----------------------------------

    <appender name="AIRBRAKE" class="hoptoad.HoptoadAppender">
        <apiKey>YOUR_API_KEY_HERE</apiKey>
        <env>production</env>
        <enabled>true</enabled>
        <endpoint>airbrake.io/notifier_api/v2/notices</endpoint>
        <secure>false</secure>

        <!-- deny all events with a level below ERROR, that is TRACE, DEBUG, INFO -->
        <filter class="ch.qos.logback.classic.filter.ThresholdFilter">
            <level>ERROR</level>
        </filter>
    </appender>

Note: `endpoint` and `secure` params are shown with default values and may be omitted.
