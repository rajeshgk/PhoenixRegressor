# PhoenixRegressor
Phoenix Performance Regression Test Suite - v1.0-SNAPSHOT

## Build
``mvn package``

## Execute
Switch to target dir and execute: <b>``java -jar PhoenixRegressor-1.0-SNAPSHOT-jar-with-dependencies.jar``</b>

Setting are in [_settings.json_](https://github.com/mujtabachohan/PhoenixRegressor/blob/master/src/main/resources/settings.json) file.

* This uses test JSONs located at [_TEST_](https://github.com/mujtabachohan/PhoenixRegressor/tree/master/src/main/resources/test) directory. These test GSONs include Phoenix DDL, DML and basic rules for data upserts.
* _RESULT_ path stores individual test result GSONs
* __PUBLISH PATH_ path stores HTML results. See _HTML Publishing_ section below
* _ITERATIONS_ number of iterations to run query for and pick the lowest execution time
* _LOAD DATA_ reload synthetic CSV data

If you want to compare say, two different Phoenix versions, change Phoenix version in _pom.xml_ and update label in _settings.json_, compile and execute. Also do update your HBase server with new Phoenix jar, wipe all tables and restart server before you begin your test. Now you would get multiple result files in RESULT directory based on different labels that can be used for comparison.

## HTML Publishing
<b>``java -jar PhoenixRegressor-1.0-SNAPSHOT-jar-with-dependencies.jar publish``</b>

This will produce comparison graphs in HTML located at _PUBLISH_PATH_ based on all the result files available in RESULT directory

