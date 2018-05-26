![DDT Framework Functional Testing - Pass](https://img.shields.io/badge/DDT%20Framework%20|%20Functional%20%20-pass-green.svg?longCache=true&style=for-the-badge)<br>
![DDT Framework Security Testing - Pass](https://img.shields.io/badge/DDT%20Framework%20|%20Security%20%20%20%20%20%20-pass-green.svg?longCache=true&style=for-the-badge) <br>
![DDT Framework Performance Testing - Pass](https://img.shields.io/badge/DDT%20Framework%20|%20Performance-fail%20-red.svg?longCache=true&style=for-the-badge)
# Automated API DDT (Data-Driven Test) Framework
## Overview

API Data-driven testing (DDT) describes a way of testing where test input data and assertions keys and expected values are all driven from a table. Typically the table is a spreadsheet with every row represent a test step or an API call.

The advantage of DDT is the ease to add additional rows to the spreadsheet when new test scenarios are added to the product (API) under test. Also, in DDT, the test environment settings and control are not hard-coded. 

This API DDT Framework is developed using SmartBear ReadyAPI product. To use the framework you will have to get a license or you can download the trial version of SmartBear ReadyAPI.

If you adopt this framework for your API testing, you are not only going to save a lot of time and money, you would also easily add security and performance testing to your API product testing without any extra effort as both tests are embedded in this DDT framework.

## 1. Read the article at my blog
Before you go any further, it is better to go through the article I published in my blog titled [DX: How to boost the performance of your APIs - Part I](https://www.earth2.digital/blog/How-to-boost-the-performance-of-your-APIs-1-adam-ali.html)
## 2. Check out to create git repository on your machine?
1. Create new directory
```
$ mkdir api-ddt-framework
$ cd api-ddt-framework
```
2. Initialize git repository in the newly created directory
```
$ git init
Initialized empty Git repository in /Users/{username}/Downloads/api-ddt-framework/.git/
$
```
3. Get a copy of this repo

```
$ git clone git@github.com-{gihubUsername}:earth2digital/automated-api-ddt-framework.git
Cloning into 'automated-api-ddt-framework'...
Enter passphrase for key '/Users/{Username}/.ssh/id_rsa': 
Enter passphrase for key '/Users/{Username}/.ssh/id_rsa': 
remote: Counting objects: 126, done.
remote: Compressing objects: 100% (109/109), done.
remote: Total 126 (delta 62), reused 58 (delta 15), pack-reused 0
Receiving objects: 100% (126/126), 83.42 KiB | 199.00 KiB/s, done.
Resolving deltas: 100% (62/62), done.
$ 

```
## 3. Open Automated API DDT Framework using SmartBear ReadyAPI

![ReadyAPI Import Composite Project](https://media-assets.myprototype.com.au/github/images/ReadyAPI-import-composite-project-v2.png)


## 4. Open the spreadsheet and update it with your test scenarios
The excel spreadsheet included in the API DDT Farmework, has an Overview Sheet and multiple other sheets. The Overview sheet contains the overview of the Microservices that is the scope of testing. The location column highlighted in red determine which sheet/s in scope for testing. 

The API DDT Framework loops on the list in that column to get all the sheets in-scope and execute all the test steps included in every sheet. If you want to skip one of the sheets from testing, you can do so by removing it's location value from the column highlighted in red or remove the whole row.

![API DDT Framework Spreadsheet - Overview Sheet](https://media-assets.myprototype.com.au/github/images/API-DDT-Spreadsheet-01-v2.png)
## 5. Run Functional Test
saasasasa
## 6. Run Security Test
saasasasa
## 7. Run Performance Test
saasasasa
## 8. Check out the generated test report
