# Python SDK tests

The test suite uses Python's standard library and the built-in **unittest** 
library. The Splunk Enterprise SDK for Python has been tested with Python v3.7 
and v3.9.

TODO: info about using tox.

TODO: info about different types of tests (unit/integration/system) + need to setup docker for integration and system.

## Running tests

- running without -f will run on currently active python version
- Run unit tests on all python versions:

 `tox -f unit`

- running all tests (unit, integration and system)
  - `tox`

- running specific test
- running type of test on only one python version
- 




NOTE: Before running the test suite, make sure the instance of Splunk you
are testing against doesn't have new events being dumped continuously
into it. Several of the tests rely on a stable event count. It's best
to test against a clean install of Splunk, but if you can't, you
should at least disable the *NIX and Windows apps. Do not run the test
suite against a production instance of Splunk! It will run just fine
with the free Splunk license.


## Code Coverage

Code coverage is also provided with `pytest-cov` which uses `Coverage.py` under the hood. The code coverage stats are displayed at the end of each tox test run.

## Test reports

Pytest also generates test reports in JUnit XML format.  For each tox environment, the test reports are saved in `test-reports/junit-{test-env}.xml`
