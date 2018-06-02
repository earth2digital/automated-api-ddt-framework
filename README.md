![DDT Framework Functional Testing - Pass](https://img.shields.io/badge/Testing%20DDT%20Framework%20|%20Functional%20%20-pass-green.svg?longCache=true&style=for-the-badge)<br>
![DDT Framework Security Testing - Pass](https://img.shields.io/badge/Testing%20DDT%20Framework%20|%20Security%20%20%20%20%20%20-pass-green.svg?longCache=true&style=for-the-badge) <br>
![DDT Framework Performance Testing - Pass](https://img.shields.io/badge/Testing%20DDT%20Framework%20|%20Performance-fail%20-red.svg?longCache=true&style=for-the-badge)
# Automated API DDT (Data-Driven Test) Framework
## Overview

API Data-driven testing (DDT) describes a way of testing where test input data and assertions keys and expected values are all driven from a table. Typically the table is a spreadsheet with every row represent a test step or an API call.

The advantage of DDT is the ease to add additional rows to the spreadsheet when new test scenarios are added to the product (API) under test. Also, in DDT, the test environment settings and control are not hard-coded. 

This API DDT Framework is developed using SmartBear ReadyAPI product. To use the framework you will have to get a license or you can download the trial version of SmartBear ReadyAPI.

If you adopt this framework for your API testing, you are not only going to save a lot of time and money, you would also easily add security and performance testing to your API product testing without any extra effort as both tests are embedded in this DDT framework.

## 1. Read the article at my blog
Before you go any further, it is better to go through the article I published in my blog titled [How to boost the performance of your APIs - Part I](https://www.earth2.digital/blog/How-to-boost-the-performance-of-your-APIs-1-adam-ali.html)

## 2. Create a git repository on your machine and get a copy of this repository
1. add your github ssh identity
```
$ ssh-add ~/.ssh/id_rsa
Enter passphrase for /Users/{Username}/.ssh/id_rsa:
Identity added: /Users/{Username}/.ssh/id_rsa (/Users/{Username}/.ssh/id_rsa)
$ 
```
2. Check if identity got added
```
$ ssh-add -l
2048 SHA256:91TnoNM/aH6+1/iajdcMEQ+Ymre1+yX/O/yBdy6FHeE /Users/{Username}/.ssh/id_rsa (RSA)
$
```
3. Get a copy of this repo

```
$ github clone git@github.com:earth2digital/automated-api-ddt-framework.git
Cloning into 'automated-api-ddt-framework'...
remote: Counting objects: 196, done.
remote: Total 196 (delta 0), reused 0 (delta 0), pack-reused 196
Receiving objects: 100% (196/196), 113.89 KiB | 277.00 KiB/s, done.
Resolving deltas: 100% (99/99), done.
$ 
$ ls -ltr automated-api-ddt-framework
total 624
-rw-r--r--  1 yakov  staff   42929 27 Apr 17:33 API-Automated-QA-Template.xlsx
-rw-r--r--  1 yakov  staff    3216 27 Apr 17:33 CODE_OF_CONDUCT.md
-rw-r--r--  1 yakov  staff     141 27 Apr 17:33 CONTRIBUTING.md
drwxr-xr-x  5 yakov  staff     160 27 Apr 17:33 GenericTestSuite
-rw-r--r--  1 yakov  staff   35147 27 Apr 17:33 LICENSE
-rw-r--r--  1 yakov  staff   15665 27 Apr 17:33 LoadTest.xml
drwxr-xr-x  5 yakov  staff     160 27 Apr 17:33 LoginService
-rw-r--r--  1 yakov  staff     734 27 Apr 17:33 PULL_REQUEST_TEMPLATE.md
-rw-r--r--  1 yakov  staff    8233 27 Apr 17:33 README.md
drwxr-xr-x  5 yakov  staff     160 27 Apr 17:33 ScenarioGenericService
-rw-r--r--  1 yakov  staff  179459 27 Apr 17:33 SecurityTest.xml
-rw-r--r--  1 yakov  staff      26 27 Apr 17:33 _config.yml
-rw-r--r--  1 yakov  staff      53 27 Apr 17:33 element.order
drwxr-xr-x  3 yakov  staff      96 27 Apr 17:33 reports
-rw-r--r--  1 yakov  staff    4647 27 Apr 17:33 settings.xml
$ 

```
## 3. Download SmartBear ReadyAPI

Download and install SmartBear ReadyAPI v2.3 trial version or use the 2.3 licensed version you have. The API DDT Framework uses the latest features in SmartBear ReadyAPI so you will have to upgrade to version 2.3 if you have an earlier version.

[SmartBear ReadyAPI Trial Download](https://smartbear.com/product/ready-api/free-trial/)

## 4. Open Automated API DDT Framework using SmartBear ReadyAPI

![ReadyAPI Import Composite Project](https://media-assets.myprototype.com.au/github/images/ReadyAPI-import-composite-project-v2.png)


## 5. Open the spreadsheet and update it with your test scenarios
### 1. Overview Sheet

The excel spreadsheet included in the API DDT Farmework, has 2 types of spreadsheets, an Overview Sheet and a Microservice sheet. The Overview sheet contains the overview of the Microservices that is the scope of testing. The location column highlighted in red determine which sheet/s in scope for testing.

![API DDT Framework Spreadsheet - Overview Sheet](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-01-v2.png)

The API DDT Framework loops on the list in that column to get all the sheets in-scope and execute all the test steps included in every sheet. Every sheet represent a Microservice to be tested. If you want to skip one of the sheets (Or Microservices) from testing, you can do so by removing it's location value from the column highlighted in red or remove the whole row.

![API DDT Framework Spreadsheet - Sheets](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-02.png)

### 2. Microservice Sheet
The Microservice sheet has all the test steps that need to be executed in all test scnarios for a particular Microservice. In this example we have 5 Microservices to be tested:

- Account
- Notification
- Order
- Connection

Every Microservice sheet has 2 sets of test input data, Request Parameters and Response Assertions. The API DDT Framework supports up to 13 assertions on the API Response. The assertions are of two types, HTTP response code and JSON response message payload. For the response message payload type, you can define any key you want using JSON Path (to be retrieved from the JSON payload in the response) and expected value using just normal text or another JSON Path in the response message.

The Microservice sheet also has a column called "Run" highlighted in red. That column can be used to mark steps to be skipped from testing. All you need to do is to set it to true or false for whether to have the step run or not.

![API DDT Framework Spreadsheet - Microservice sheet](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-03.png)

For now, you can choose to update the sheets accordingly and run the API DDT Framework or you can just run it without doing any updates as the example sheets have been tested to be working fine for Functional, Security and Performance testing. Although performance testing needs a bit of a tweak to give accurate results.

## 6. Run Functional Test

To run the Functional Test cases, just select the project name on the left handside menu "GenericProject_v7" and then click the green play arrow highlighted in red.

![API DDT Framework Spreadsheet - Functional Test](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-04-v3.png)

## 7. Run Security Test

To run the Security Test cases, just select the Test Suite on the left handside menu "SecurityTest" and then click the green play arrow highlighted in red.

![API DDT Framework Spreadsheet - Security Test](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-05.png)

## 8. Run Performance Test

To run the Performance Test cases, just select the Test Suite on the left handside menu "LoadTest" and then click the green play arrow highlighted in red.

![API DDT Framework Spreadsheet - Performance Test](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-06.png)

## 9. Run all tests as part of CI/CD Pipeline using command line

1. Run Functional Test

```
$ sudo /opt/SmartBear/ReadyAPI-2.3.0/bin/testrunner.sh -e https://api.myprototype.com.au -FPDF -R"Project Report" /Users/{username}/downloads/api-ddt-framework/automated-api-ddt-framework  -f /Users/{username}/downloads/api-ddt-framework
$ 

```

2. Run Security Test

```
$ sudo /opt/SmartBear/ReadyAPI-2.3.0/bin/securitytestrunner.sh /Users/{username}/downloads/api-ddt-framework/automated-api-ddt-framework -c "SecurityTest" -d https://api.myprototype.com.au -FPDF -R"SecurityTest Report" 
$ 

```

2. Run Performance Test

```
$  sudo /opt/SmartBear/ReadyAPI-2.3.0/bin/loadtestrunner.sh  -E test -FPDF /Users/{username}/downloads/api-ddt-framework/automated-api-ddt-framework  -n "LoadTest" -S  "Arriving VU/s,Time Taken" 
$ 

```

## 10. Check out the generated test report

To run the project report, just select the Project Name on the left handside menu "GenericProject_v7" and then click the gray report icon highlighted in red.

![API DDT Framework Spreadsheet - Performance Test](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-07.png)

To save the report as PDF or any other format, click on the save icon highlighted in red.

![API DDT Framework Spreadsheet - Performance Test](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-08.png)

## AWS Linux Tip

While running the test cases using command line, you might experience problems as the microsoft fonts are not installed on AWS Linux. To solve the issue, execute the below commands:

```
$ wget http://corefonts.sourceforge.net/msttcorefonts-2.5-1.spec
$ wget https://www.cabextract.org.uk/cabextract-1.6-1.i386.rpm
$ sudo yum install cabextract-1.6-1.i386.rpm
$ sudo yum install -y rpmdevtools rpm-build
$ rpmbuild -ba msttcorefonts-2.5-1.spec
$ sudo yum install /home/ec2-user/rpmbuild/RPMS/noarch/msttcorefonts-2.5-1.noarch.rpm

```
