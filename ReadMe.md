NBA Automation Framework Java 17 | Selenium | BDD | API

Overview

**NBA-Automation-Framework-FinalWithAPI-Java17-BDD-Full** is a **hybrid, multi-module test automation framework** designed for enterprise-grade UI and API testing.  
It follows a **modular, scalable, and extensible architecture** combining **Selenium WebDriver**, **TestNG**, **Cucumber BDD**, and **Rest-Assured** to enable full-stack automation across both UI and service layers.

This project demonstrates **best practices for test automation engineering** — including Page Object Model (POM) design, BDD-driven test development, Maven-based modular builds, and advanced reporting using **Extent Reports**.

Framework Modules

| Module | Description |
|---------|--------------|
| **automation-framework** | Core reusable components — WebDriver factory, environment management, base classes, utilities, logging, and reporting integrations. |
| **core-tests** | UI automation layer using Java + TestNG + Selenium + Cucumber. Handles NBA web application scenarios via Page Object Model. |
| **api-tests** | API automation module using Rest-Assured for validation of RESTful endpoints, schema verification, and data consistency checks. |

Technology Stack

| Category | Tool / Library | Purpose |
|-----------|----------------|----------|
| **Language** | Java 17 | Core programming language for all modules |
| **Build Tool** | Apache Maven 3.9+ | Dependency management and build lifecycle orchestration |
| **Test Runner** | TestNG 7.11.0 | Test orchestration and suite execution |
| **BDD Framework** | Cucumber JVM | Behavior-driven development using Gherkin syntax |
| **UI Automation** | Selenium WebDriver 4.x | Browser automation and web UI interaction |
| **API Testing** | Rest-Assured 5.x | RESTful API validation and schema verification |
| **Reports** | Extent Reports + Extent Cucumber Adapter | Interactive HTML reports for UI and API test results |
| **Logging** | SLF4J + Log4j2 | Centralized, configurable logging mechanism |
| **Data Handling** | Apache POI / Jackson | Data-driven testing using Excel and JSON |
| **Driver Management** | Selenium Manager | Automatic browser driver download and setup |
| **IDE Support** | IntelliJ IDEA / Eclipse | Fully compatible development environments |


Framework Architecture

1. Base Layer
Defines reusable setup and teardown logic (`BaseTest`), driver initialization, and environment configuration management.

2. Utilities Layer
Contains helper classes for:
- File handling  
- Data readers (Excel, JSON, CSV)  
- WebDriver waits and synchronization  
- Screenshot capture  
- Logging and timestamp management  

3. Page Object Model (POM)
Implements a **clean separation of UI locators and actions**, ensuring code reusability, scalability, and maintainability.

4. BDD Layer (Cucumber)
- Feature files written in **Gherkin syntax** describe user scenarios.
- Step definitions map Gherkin steps to executable Java methods.
- Extent Cucumber Adapter consolidates results into unified HTML reports.

5. API Testing Layer
- Uses **Rest-Assured** for RESTful service validation.
- Supports GET, POST, PUT, DELETE methods.
- Includes JSON schema validation, response code checks, and response time assertions.

6. Reporting Layer
- **Extent Reports** generate interactive HTML dashboards for UI and API execution.
- Screenshots embedded automatically for failed steps.
- Reports are generated under:
  target/reports/
 

Execution

Run Entire Suite
mvn clean test -DsuiteXmlFile=testng.xml

Run Specific Module
mvn -pl core-tests -am test
mvn -pl api-tests -am test

Run Specific Test Class
mvn -pl core-tests -am -Dtest=DP2_FooterLinksTest test

Run Cucumber BDD Tests
mvn test -Dcucumber.features="src/test/resources/features" -Dcucumber.filter.tags="@Regression"

Reporting

Reports are automatically generated in:
core-tests/target/reports/
api-tests/target/reports/

Each report provides:
- Execution summary and statistics  
- Environment and browser configuration details  
- Step-by-step logs and embedded screenshots  
- Pass/fail/skip breakdowns with duration insights  

Best Practices Followed

Modular, layered design enabling high maintainability  
Parallel execution supported via TestNG configurations  
CI/CD integration ready for Jenkins, GitHub Actions, or GitLab CI  
Robust error handling and retry mechanism for flaky tests  
Unified reporting for both UI and API test executions  
Adherence to SOLID principles and clean code practices  

Prerequisites

| Requirement | Minimum Version |
|--------------|----------------|
| **Java** | 17 or higher |
| **Apache Maven** | 3.9+ |
| **IDE** | Eclipse / IntelliJ IDEA |
| **Browsers** | Chrome / Edge / Firefox |
| **Network** | Internet connection required for Selenium Manager 

Folder Structure

NBA-Automation-Framework/

automation-framework/
src/main/java/com/nba/framework/base/
src/main/java/com/nba/framework/utils/
pom.xml

core-tests/
src/test/java/com/nba/tests/
src/test/resources/features/
pom.xml

api-tests/
src/test/java/com/nba/api/
pom.xml

pom.xml (Parent)

CI/CD Integration (Optional)
To execute via CI pipelines:
mvn clean test -DsuiteXmlFile=testng.xml

Artifacts (Extent HTML reports, logs, screenshots) can be archived and published using Jenkins or GitHub Actions for continuous visibility.

Future Enhancements

- Dockerized Selenium Grid execution  
- Integration with Allure or ReportPortal  
- Cloud execution support (BrowserStack, LambdaTest, SauceLabs)  
- AI-assisted self-healing locators and intelligent test data generation  


Contributors

**Primary Author:** Sanjeev Nandivada
**Role:** QA Automation Architect / Manager  
**Expertise:** Java, Selenium, BDD, API Testing, AI-driven Automation, Framework Design  


> This framework represents a production-grade test automation setup demonstrating modern practices, modularization, and CI/CD readiness for scalable enterprise testing.
