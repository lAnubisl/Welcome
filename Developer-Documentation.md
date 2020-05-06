
## OpenMAVN
### Documentation for Community Developers
![OpenMAVN logo](https://lh4.googleusercontent.com/-wP94tQuSoP4wwhKqHchJFZ9QVTiZ4_ZOOOFjg2Z7Ej1LKOpR9Gfe1L7l7cCOt51KbqxbOVKz-LlLWNux9fsGelzPoLvzKHzSCgKTrJxFzwteG6RB5KPB6keznmMc-uK2CNfyEPm)



## Table of Contents  

- [General product overview](#general-product-overview)
- [Primary expected user scenarios](#primary-expected-user-scenarios)
- [Technology stack](#technology-stack)
- [Hosting environment](#hosting-environment)
- [Logging/Monitoring Suite](#logging-monitoring-suite)
- [Development tools](#development-tools)
- [External services integration](#external-services-integration)
- [Project components](#project-components)
- [Development environment setup](#development-environment-setup)
- [Tickets dashboard](#tickets-dashboard)
- [Useful Links](#useful-links)


<a name="general-product-overview"/>

## **General product overview**

MAVN is an abbreviation of the word “MAVEN”, which came from Yiddish and means “one, who understands”. It does not have any relationship with Apache Maven.

MAVN Alliance has been built up as a global community in reaction to the crisis triggered/caused by COVID-19 to support all the efforts to keep our businesses and economy running as well as to strengthen solidarity between each other.

MAVN Alliance aims to support small and midsize businesses during the crisis and beyond, and to create new ways of supporting and interacting with each other. 

OpenMavn is a platform that helps to manage Smart Vouchers for small and medium businesses (SME’s) during crisis time. It has a mobile application for business owners and their clients as well as platform administration portal and integration API.


<a name="primary-expected-user-scenarios"/>

## **Primary expected user scenarios**

Here are the 6 steps of how it works for SMEs and their clients:

#### STEP 1:
SME registers to the platform.

#### STEP 2:
SME creates a voucher campaign. 
It might be required to pay for blockchain operations (depends on the underlying blockchain, for the moment this fee is 0).  
 
#### STEP 3:
Customer buys a voucher by paying via a 3rd party payment gateway.

#### STEP 4:
SME receives funding to his account.

#### STEP 5:
Customer receives the digital voucher.

#### STEP 6:
Customers can redeem the voucher at the SME, or send it as a gift to a friend or relative, or exchange for another voucher with friends.


<a name="technology-stack"/>

## **Technology Stack**

**C#** - the base backend programming language, the reason for selection is that most of our internal dev team has experience in it.

**C#, JavaScript, Angular 9** - programming languages for frontend, the reason for selection: most of our internal development team has experience in it.

**Flutter** - programming language for mobile app. We choose it because of a single code base for both Android and iOS, which is actively supported by Google.

**Docker** - modern technology for running isolated environments for components. The reason for selection: it’s de-facto an industry standard.

**Kubernetes** - DevOps tool that allows easy management of running dockerized components. The reason for selection: it’s de-facto an industry standard.

**Redis** - in-memory key-value store, used as a cache. The reason for selection. It was a good choice for the distributed cache.

**RabbitMq** used as a system event bus. The reason for selection: it has decent performance for small and medium-size systems, and has a low learning threshold.

**Microsoft SQL Server** - relational database.

**Azure storage service** - used for storing logs, blob files and message queues, legacy reasons for selection. We are going to replace azure storage services with something else in future.

**Azure services such as KeyVault, Blockchain** used mostly for the blockchain part of the system. The reason for selection: the system is Azure dependant ATM, so these were easily accessible components that solved required needs.

**Sendgrid** as email notifications service.

**Firebase Cloud Messaging** used for sending push notifications to mobile, selected as a free option that has required support and Flutter plugins.

**Entity Framework** - .NET ORM, selected as the most familiar ORM for most Net developers.


<a name="hosting-environment"/>

## **Hosting environment**

We have one internal Kubernetes environment for OpenMAVN. Unfortunately, only internal developers have access to it. An OpenVPN client with the corresponding configuration is required for accessing it.

Community developers would need to run components locally. Follow this 
[Instruction about how to do it](https://github.com/OpenMAVN/Welcome/blob/master/how-to-run-backend.md).


<a name="logging-monitoring-suite"/>

## **Logging/Monitoring Suite**

**Internal environment:**
All logs are stored in Azure Storage Account (TableStorage). There is no monitoring suite yet. In the future we will probably be going to use ElasticSearch + Logstash + Kibana (ELK).

Slack integration is possible, it’s configuration is in progress. It can be used for applications health monitoring, errors and warnings control.

**Local run:**
Only searching through logs in the Azure storage emulator is available.


<a name="development-tools"/>

## **Development tools**

-   Backend components are developed using VS 2017/2019 or Rider.
-   Frontend IDE is VC Code.
-   Usual IDE - for mobile development is Android studio.
-   Github organization - [https://github.com/OpenMAVN](https://github.com/OpenMAVN).
-   For CI/CD builtin are used Github Actions.
-   Only unit tests are used for automated testing. Overall unit testing coverage is available [here](https://github.com/OpenMAVN/Welcome/blob/master/Components.md).
-   Built docker images are pushed to [docker hub](https://hub.docker.com/u/openmavn).
-   Built nuget packages are pushed to [nuget.org](https://www.nuget.org/profiles/OpenMAVN)

Usually, each component has a contribution starting point (file CONTRIBUTING.md) in its repository.


<a name="external-services-integration"/>

## **External services integration**

**Sendgrid** as email notifications service.
[**Payrexx**](https://www.payrexx.com/en/home/) is a payment gateway.
**Firebase Cloud Messaging** is used for sending push notifications.


<a name="project-components"/>

## **Project components**

**[Google sheet with a short description of system components](https://docs.google.com/spreadsheets/d/103WVbFb-o9hUBoXcbBmVH9npXijVWcHOwuNXdHD4mGY/edit?usp=sharing).**


<a name="development-environment-setup"/>

## **Development environment setup**

OpenMAVN is a system that consists of many individual microservices. Some of them are dependent on others. In order to run the entire system locally it is required to:

-   Run all microservices locally. This method has need downloading each individual service from GitHub or DockerHub, configure ports and connectionStrings, and run them.

or

-   Run service(s) that you are working on and mock external dependencies using HTTP API mocking tools like [Mockoon.com](https://mockoon.com/). This method does not require all services to be running but it requires additional mocking profiles development and support.

Both ways are not ready by 100% and until then there is a third option available for trusted contributors:

-   Connect to OpenMAVN development network through VPN where development kubernetes cluster is running. Download and configure individual service(s) you are going to work on and having all other services accessible through VPN everything will be working.

If you are an engineer from a partner's company please use [this instruction](https://github.com/OpenMAVN/Welcome/blob/master/vpn-connection-configuration.md) to get VPN access.


<a name="tickets-dashboard"/>

## **Tickets dashboard**

Link to *.md file with these requirements on GIthub.


<a name="useful-links"/>

## **Useful Links**

Here we listed channels and sources you might want to add to stay up-to-date with the project.

[Mavn.ch](https://mavn.ch) - official website of the Initiative.
[LinkedIn](https://www.linkedin.com/showcase/42289145/) - account about Alliance with news about it.
[Twitter](https://twitter.com/AllianceMavn) - account about Alliance with news about it.
[Telegram chat](https://t.me/mavnAllianceGroup) - community group for every member of the MAVN Alliance.
[Slack](https://join.slack.com/t/openmavn/shared_invite/zt-d1bku3gj-IUrfs36DHYkJ4D~l~DgUbQ) - communication channel for developers team.
