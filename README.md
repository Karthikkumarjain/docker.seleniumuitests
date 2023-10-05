
# Dockerizing Test Automation Framework

This is a sample test automation framework using POM in Selenium. The framework is built on Selenium along with TestNG and other dependencies.


## Prerequisite

Since this is based on Selenium with Java, so the pre-requisite is to have Java installed on our system. Once Java is installed.

* Clone the repo
* Build the project with maven
* See the Run Tests section on how to run the tests
## Structure

The primary directories are as follows


* src/main/java - Contains the main code
* src/main/resources - Contains the resources required for the tests
* src/test/java - Contains the test code
* src/test/resources - Contains the test resources
* target - Contains the reports and logs
* pom.xml - Contains the dependencies required for the project
* default.properties - Contains the global level properties
* Dockerfile - Contains the docker commands to build the image
* 
## System Under Test

The system under test are
* https://d1uh9e7cu07ukd.cloudfront.net/selenium-docker/reservation-app/index.html
* https://d1uh9e7cu07ukd.cloudfront.net/selenium-docker/vendor-app/index.html

## Libraries Used

* Selenium
* TestNG
* Logback
* Maven
* Docker
* Jenkins
* jackson


## Run Tests

To run the tests in local use


```bash
docker build -t=karthikkumarjain/seleniumondocker .


```
```bash
docker compose up
```
If you dont want to use compose.yaml file-
```bash
docker run -e BROWSER=chrome -e HUB_HOST=localhost -e TEST_SUITE=flight-reservation.xml -e THREAD_COUNT=4 karthikkumarjain/seleniumondocker
```
## Reports

* Reports can be found under target/test-output/emailable-report.html