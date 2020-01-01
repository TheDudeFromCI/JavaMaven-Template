[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=TheDudeFromCI_JavaMaven-Template&metric=alert_status)](https://sonarcloud.io/dashboard?id=TheDudeFromCI_JavaMaven-Template)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=TheDudeFromCI_JavaMaven-Template&metric=bugs)](https://sonarcloud.io/dashboard?id=TheDudeFromCI_JavaMaven-Template)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=TheDudeFromCI_JavaMaven-Template&metric=coverage)](https://sonarcloud.io/dashboard?id=TheDudeFromCI_JavaMaven-Template)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=TheDudeFromCI_JavaMaven-Template&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=TheDudeFromCI_JavaMaven-Template)
[![Technical Debt](https://sonarcloud.io/api/project_badges/measure?project=TheDudeFromCI_JavaMaven-Template&metric=sqale_index)](https://sonarcloud.io/dashboard?id=TheDudeFromCI_JavaMaven-Template)

---

# Java + Maven Template
This project is designed to be a template repository for setting up a simple Java and Maven based project with support for CI through the use of Github Actions and Sonar Cloud.

### Default Configuration
The configuration is currently setup with several common testing frameworks (JUnit, Mockito, and Awaitility) and a logging library (SLF4J). The project will automatically attempt to deploy to Github Packages after every push to the master branch. The project is tested and scanned after every push or pull request to any branch. Test and scan requests are deployed to SonarCloud.

### Setup Steps:
This project is largely setup in advance, however a few minor tweaks need to be made to fit your project's needs.
* Setup the project on SonarCloud, to prepare the project Token (referred to as project.login on SonarCloud), project key, and organization. Select "Other Tools" when asked which build tool you use, and select "Maven" on the next page. Use the "mvn verify sonar:sonar" command, as specified by SonarCloud, on your local repo for the project.
* Place the Sonar Token in the Github secrets with the name SONAR_TOKEN.
* Update the properties area in pom.xml with the project key and organization.
* Update the distributionManagement area in pom.xml with your organization name and project name. Make sure to leave your organization name in all lowercase.
* In .github/workflows/maven.yml, near the bottom of the file, replace the username with your organization. Leave this value in all lowercase.
* Lastly, replace this readme with the desired readme for your project. If you wish to keep the project badges in this readme, simply update the URLs to match the respective URLs of your project, following the same format. (Replacing "TheDudeFromCI_JavaMaven-Template" with your organization name-underscore-your project name.)