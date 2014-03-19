p6spy-perf
==========

performance tests for [p6spy](https://github.com/p6spy/p6spy) project 

**Running the tests yourself:**

1. run:

        mvn clean verify

1. check the results in:

        target/results/*-p6spy-perf.html

    the most valuable part seems to be present in the:

        target/results/*-durations-*-p6spy-perf.html

    in the "average" column (values are in miliseconds).
