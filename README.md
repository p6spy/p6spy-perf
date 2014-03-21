p6spy-perf
==========

performance tests for [p6spy](https://github.com/p6spy/p6spy) project 

**Running the tests:**

1. run:

        mvn clean verify

1. check the results in:

        target/results/*-p6spy-perf.html

    the most valuable part seems to be present in the:

        target/results/*-durations-*-p6spy-perf.html

    in the "average" column (values are in miliseconds).

**Profiling the tests with [Yourkit](http://www.yourkit.com/download/index.jsp):**

1. (optional step) don't need to run non-p6spy JMeter tests => disable it in:

         src/test/jmeter/p6spy-perf.jmx
         
   in JMeter UI or via modifying:
        
         - <JDBCSampler guiclass="TestBeanGUI" testclass="JDBCSampler" testname="no-p6spy select" enabled="true">
         + <JDBCSampler guiclass="TestBeanGUI" testclass="JDBCSampler" testname="no-p6spy select" enabled="false">
            
1. install Yourkit + start it
1. run:

        mvn clean verify -P yourkit -Dyourkit.agent.path=<path to yourkit agent representing "-agentpath">

1. cpu tracing starts automatically => open the "ApacheJMeter" VM in the Yourkit UI (section "Monitor Local Applications") and
1. once test finish, feel free to analyze the results in Yourkit
