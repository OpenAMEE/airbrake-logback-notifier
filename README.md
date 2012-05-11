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
        <param name="api_key" value="YOUR_API_KEY_HERE"/>
        <param name="env" value="production"/>
        <param name="enabled" value="true"/>
        <param name="endpoint" value="airbrake.io/notifier_api/v2/notices"/>
        <param name="secure" value="false"/>

        <!-- deny all events with a level below ERROR, that is TRACE, DEBUG, INFO -->
        <filter class="ch.qos.logback.classic.filter.ThresholdFilter">
            <level>ERROR</level>
        </filter>
    </appender>

Note: `endpoint` and `secure` params are shown with default values and may be omitted.
